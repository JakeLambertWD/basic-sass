SETUP:

// install SASS on VS Code
In the store: live sass complier

// SASS auto sets up style.css file
Click Watch Sass button at bottom of the window

// Upon saving your files, SASS will add all the 
   prefixes for the different browsers that dont 
   necessarily support some css features


LEARNT: 

// Custom CSS variables, contain specific values 
   to be reused throughout a document.
   Allows a value to be stored in one place, 
   then referenced in multiple other places 

$primaryBtn: blue;

header {
	background: $primaryBtn;
	display: flex;
	justify-content: center;
}

///////////////////////////////////////////////
// Nesting (i.e. nest the button in the header)

header {
	background: lightblue;
	display: flex;
	justify-content: center;
	color: $textColor;
	button {
		background: $primaryBtn;
	}
}

////////////////////////////////////////////
// Use the & symbol, to add hover, focus etc
header {
	background: lightblue;
	display: flex;
	justify-content: center;
	color: $textColor;
	button {
		background: $primaryBtn;
		&:hover {
			background: green;
		}
	}
}

///////////////////////////////////////////////
// Breakdown CSS file into multiple files

// Create file
_header.scss
// In style.scss link to file
@import './header';

////////////////////////////////////////////
// SASS Mixins are like JS functions

// To reference you will call it like a function()

@mixin flexCenter {
	height: 100vh;
}

header {
	@include flexCenter();
}

/////////////////////////////////////////////
// Parse in parameters to Mixins
@mixin flexCenter($direction, $background) {
	flex-direction: $direction;
	background: $background;
}

header {
	@include flexCenter(column, red);
}

////////////////////////////////////////////
// Inherit styles from another file w/ @extend

@import './header';

.contact {
	@extend header;
}

////////////////////////////////////////////////
// Overwrite proeprties

@import './header';

.contact {
	@extend header;
	background: lightcoral;
}
