@import 'bourbon'; // http://bourbon.io/

@import '../partials/layout'; // responsive grid and media queries

// color palette - these colors will be the color swatches of the Colors section

$color-1: #17B212; //
$color-2: #F8FBFC; // background
$color-3: #3575D3; // BlueHost-blue
$color-4: #D7DBE0; // border-grey
$color-5: #F72F26; // danger-red
$color-6: #15315A; // dark-blue
$color-7: #009013; // dark-green
$color-8: #5C5C5C; // dark-grey
$color-9: #F1F5F7; // inactive-button
$color-10: #9DAFBD; // inactive-text
$color-11: #9A9A9A; // light-grey
$color-11: #FAFBFC; // lightest-grey
$color-11: #F89C24; // warning-orange
$color-11: #ffffff; // white

// fonts

$primary-font: 'Merriweather', serif;
$secondary-font: 'Open Sans', sans-serif;

/* --------------------------------

xBackground

-------------------------------- */

body {
	/* this is the page background */
	background-color: $color-5;
}

/* --------------------------------

xPatterns

-------------------------------- */

.cd-box {
	/* this is the container of various design elements - i.e. the 2 logo of the branding section */
	border: 1px solid $color-4;
	border-radius: 3px;
	background: $color-5;
	box-shadow: 0 1px 1px rgba(#000, .05);
	padding: 6px;
}

/* --------------------------------

xNavigation

-------------------------------- */

header {
	background-color: $color-2;
}

.cd-logo {
	/* logo box style */
	background-color: $color-1;
	width: 120px;

	@include MQ(M) {
		width: 180px;
	}
}

.cd-main-nav {
	/* main navigation background color - full screen on small devices */
	background: $color-2;

	li a {
		color: $color-5;
		border-color: lighten($color-2, 5%);
	}

	@include MQ(M) {
		li a {
			color: lighten($color-2, 40%);

			&.selected {
				color: $color-5;
				box-shadow: 0 2px 0 $color-1;
			}

			.no-touch &:hover {
				color: $color-5;
			}
		}
	}
}

.cd-nav-trigger span {
	/* hamburger menu */
	background-color: $color-5;

	&::before,
	&::after {
		/* upper and lower lines */
		background-color: $color-5;
	}
}

.nav-is-visible .cd-nav-trigger span {
	/* hide line in the center on mobile when nav is visible */
	background-color: rgba($color-5, 0);

	&::before, &::after {
		/* preserve visibility of upper and lower lines - close icon */
		background-color: rgba($color-5, 1);
	}
}

.cd-download {
	/* download button top-right visible on big devices */
	background-color: lighten($color-2, 10%);

	.no-touch &:hover {
		background-color: lighten($color-2, 15%);
	}

	span {
		/* tooltip */
		background: $color-1;
		color: $color-5;

		&::before {
			/* right arrow color */
			border-color: $color-1;
		}
	}
}

/* --------------------------------

xPage title

-------------------------------- */

main > h1 {
	color: $color-2;

	@include MQ(L) {
		/* title goes into the header on big devices */
		color: $color-5;
	}
}

/* --------------------------------

xTypography

-------------------------------- */

h1, h2 {
	font-family: $secondary-font;
	color: $color-2;
}

h1 {
	font-size: 2.4rem;
	font-weight: 300;
	line-height: 1.2;
	margin: 0 0 .4em;

	@include MQ(S) {
		font-size: 3.2rem;
	}

	@include MQ(M) {
		font-size: 4rem;
	}
}

h2 {
	font-weight: bold;
	text-transform: uppercase;
	margin: 1em 0;

	@include MQ(S) {
		font-size: 1.8rem;
		margin: 1em 0 1.4em;
	}
}

section > h2::before {
	/* number before each section title */
	color: darken($color-4, 15%);
}

p {
	font-size: 1.4rem;
	line-height: 1.4;
	color: lighten($color-2, 25%);

	a {
		color: $color-1;
		text-decoration: underline;
	}

	@include MQ(S) {
		font-size: 1.6rem;
		line-height: 1.6;
	}
}

/* --------------------------------

xButtons

-------------------------------- */

.btn {
	border: none;
	box-shadow: none;
	border-radius: .25em;
	font: {
		size: 1.4rem;
		family: $secondary-font;
	}
	color: $color-5;
	padding: .6em 2.2em;
	cursor: pointer;
	background: $color-1;

	&:focus {
		outline: none;
	}

	.no-touch &:hover {
		background: lighten($color-1, 5%);
	}

	&.btn-success {
		background: $success;

		.no-touch &:hover {
			background: lighten($success, 5%);
		}
	}

	&.btn-alert {
		background: $alert;

		.no-touch &:hover {
			background: lighten($alert, 5%);
		}
	}

	&.btn-outline {
		color: $color-1;
		background: transparent;
		box-shadow: inset 0 0 0 1px $color-1;

		.no-touch &:hover {
			color: $color-5;
			background: $color-1;
		}
	}

	@include MQ(S) {
		font-size: 1.6rem;
	}
}

.cd-buttons .cd-box:nth-of-type(2) span {
	/* CSS class name color */
	color: $color-1;
}

/* --------------------------------

xIcons

-------------------------------- */

.cd-icons li {
	/* icons size */
	width: 32px;
	height: 32px;
}

/* --------------------------------

xForm

-------------------------------- */

input[type=text], select {
	border: 1px solid $color-4;
	border-radius: .25em;
	background: $color-5;

	&:focus {
		outline: none;
	}
}

input[type=text] {
	padding: .6em 1em;
	box-shadow: inset 1px 1px rgba(#000, .03);

	&.success {
		border-color: $success;
		box-shadow: 0 0 6px rgba($success, .2);
	}

	&.alert {
		border-color: $alert;
		box-shadow: 0 0 6px rgba($alert, .2);
	}

	&:focus {
		border-color: $color-1;
		box-shadow: 0 0 6px rgba($color-1, .2);
	}
}

input[type=radio],
input[type=checkbox] {
	position: absolute;
	left: 0;
	top: 0;
	margin: 0;
	padding: 0;
	opacity: 0;
}

.radio-label,
.checkbox-label {
	padding-left: 24px;
	@include user-select(none);

	&::before,
	&::after {
		/* custom radio and check boxes */
		content: '';
		display: block;
		width: 16px;
		height: 16px;
		position: absolute;
		top: 50%;
		@include transform(translateY(-50%));
	}

	&::before {
		left: 0;
		border: 1px solid $color-4;
		box-shadow: inset 1px 1px rgba(#000, .03);
	}

	&::after {
		left: 3px;
		background: url('../assets/form/icon-check.svg') no-repeat center center;
		display: none;
	}
}

.radio-label::before {
	border-radius: 50%;
}

.checkbox-label::before {
	border-radius: 3px;
}

input[type=radio]:checked + label::before,
input[type=checkbox]:checked + label::before {
	background-color: $color-2;
	border: none;
	box-shadow: none;
}

input[type=radio]:checked + label::after,
input[type=checkbox]:checked + label::after {
	display: block;
}

.cd-select::after {
	/* switcher arrow for select element */
	content: '';
	position: absolute;
	z-index: 1;
	right: 14px;
	top: 50%;
	@include transform(translateY(-50%));
	display: block;
	width: 16px;
	height: 16px;
	background: url('../assets/form/icon-select.svg') no-repeat center center;
	pointer-events: none;
}

select {
	position: relative;
	padding: .6em 2em .6em 1em;
	cursor: pointer;
	@include appearance(none);
}

@import '../partials/basic-style';
