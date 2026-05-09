let $html = document.documentElement;
let $toggle = document.createElement( "button" );

$toggle.setAttribute( "type", "button" );
$toggle.classList.add( "theme-toggle" );
$toggle.innerText = "Dark Mode";

function toggleTheme() {
	$html.classList.toggle( "dark" );
	updateButton();
}

function updateButton() {
	let dark = $html.classList.contains( "dark" );
	let label;

	if ( dark ) {
		$toggle.setAttribute( "aria-pressed", "true" );
		$toggle.innerText = "Light Mode";
		label = "Switch to light mode";
	} else {
		$toggle.setAttribute( "aria-pressed", "false" );
		$toggle.innerText = "Dark Mode";
		label = "Switch to dark mode";
	}

	$toggle.setAttribute( "aria-label", label );
}


$toggle.onclick = toggleTheme;
updateButton();
document.body.appendChild( $toggle );

let $photoDisplay = document.querySelector( "#photo-display" );
let $photos = document.querySelectorAll( ".photo" );

if ( $photoDisplay && $photos.length > 0 ) {

	function showLargePhoto( $photoFigure ) {

		if ( ! $photoFigure ) {
			return;
		}

		let $img = $photoFigure.querySelector( "img" );
		let $caption = $photoFigure.querySelector( "figcaption" );

		if ( ! $img ) {
			return;
		}

		let $largeImg = document.createElement( "img" );
		$largeImg.setAttribute( "src", $img.getAttribute( "src" ) );
		$largeImg.setAttribute( "alt", $img.getAttribute( "alt" ) );
		$largeImg.setAttribute( "width", "800" );
		$largeImg.setAttribute( "height", "600" );

		let $captionText = document.createElement( "p" );
		$captionText.classList.add( "photo-caption" );
		if ( $caption ) {
			$captionText.innerText = $caption.innerText;
		}

		let $closeButton = document.createElement( "button" );
		$closeButton.setAttribute( "type", "button" );
		$closeButton.classList.add( "close-button" );
		$closeButton.setAttribute( "aria-label", "Close enlarged photo" );
		$closeButton.innerText = "Close";
		$closeButton.onclick = clearDisplay;

		$photoDisplay.appendChild( $largeImg );
		$photoDisplay.appendChild( $captionText );
		$photoDisplay.appendChild( $closeButton );

		$photoDisplay.classList.add( "active" );
	}

	function clearDisplay() {
		while ( $photoDisplay.firstChild ) {
			$photoDisplay.removeChild( $photoDisplay.firstChild );
		}
		$photoDisplay.classList.remove( "active" );
	}

	let count = $photos.length;
	for ( let i = 0; i < count; i++ ) {

		$photos[ i ].setAttribute( "role", "button" );
		$photos[ i ].setAttribute( "aria-label", "Enlarge this photo" );
		$photos[ i ].addEventListener( "click", function() {
			showLargePhoto( $photos[ i ] );
		});

	}

}
