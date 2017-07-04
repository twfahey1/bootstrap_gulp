**** SETTING UP GULP FOR THEMING ****

-Make sure you have Node and NPM and bower installed. The package.json
should have all the necessary packages defined, so just make
sure you have it in the root folder, along with an
scss folder.

-In terminal, get to root folder,
Run "npm install". It should get all the stuff and you'll have
a "npm_modules" folder. Now you can run "gulp", and it will be
watching your "scss" folder for any new files and will auto
compile them into the dist folder! go into mixins folder and do bower install, then you can use the responsive Foundation mixins in scss... ex:

```
// Functions and Mixins
@import "../mixins/settings";
@import "../mixins/variables";
@import "../mixins/responsive";
@import "../mixins/icons";

.hero-box{
	width:100%;
	
	@include respond(medium) {
		width: 75%
	}

	@include respond(large) {
		width: 50%;
	}

}
```

Also, there is bootstrap_responsive.scss for any Bootstrap projects:

```
@import "../mixins/settings";
@import "../mixins/variables";
@import "../mixins/_bootstrap_responsive";
@import "../mixins/icons";

.hero-box{
	width:100%;
	
	@include breakpoint(md) {
		width: 75%
	}

	@include breakpoint(lg) {
		width: 50%;
	}

}
```

Also, if you make a `js` folder, it will now be compiled and minified to dist folder!

If you want to tweak *where* the output is going, look inside the gulpfile.js.
You can see what's happening there, for example, the 'watch' task is configured to watch for any changes in js and scss, but maybe you want it to also watch mixins folder for changes. You can add that line in:
```
// Watch Files For Changes
gulp.task('watch', function() {
    gulp.watch('js/*.js', ['lint', 'scripts']);
    gulp.watch('scss/*.scss', ['sass']);
    gulp.watch('scss/mixins/*.scss', ['sass']);
});
```
