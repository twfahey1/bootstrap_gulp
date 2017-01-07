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