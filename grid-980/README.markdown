
A grid layout with balanced margins and paddings. This avoids the first/last, alpha/omega rubbish that pollutes other grid layout systems on the web. This one is based on a 12-column grid of 60 pixels each with a 20 pixel gutter (made up of 10 pixels padding around each block by default).

A layout block is a child of the `.page` container, and has a `span-X` where X is the number of grid-columns the layout block spans.

The `.page` wrapper contains a 10 pixel padding, and each layout block itself a 10 pixel padding. This creates the required 20 pixel guttering between layout block content.

A `.wrap` block allows the space inside it to be split down further with `.span` layout blocks. Essentially, the `.wrap` is a margin-less and padding-less layout block, so it allows inner layout blocks to use their consistent layout padding to keep the gutter widths consistent.

In situations where a layout block needs a close-cropped border, the set of `.unbleed`, `.hunbleed` and `.vunbleed` classes swap a layout block's 10 pixel paddings out for 10 pixel margin, so that a border can be applied to that layout block horizontally, vertically or both. 

The `.flush`, `.hflush` and `.vflush` classes is for full-width layout blocks . It grabs the padding of the containing `.page` as it's own padding too. This is useful for a full-width background-colour header that stretches the entire width of the `.page` container, including all the guttering.

base.css
--------

Sets the site-wide baseline style


grid.css
--------

An example of a typical page layout:

	<div class="page">
		<div class="page-header  span-12 hflush"></div>
		<div class="page-content span-8"></div>
		<div class="page-related span-4"></div>
		<div class="page-footer  span-12"></div>
	</div>

Sets up the simple grid classes, plus a few handy overrides for bleeding into the gutter. Classes for layout blocks:

* `span-1` ... `span-12` - sizes a block from one grid column through to 12 with a default left float
* `rspan-1` ... `rspan-12` - sizes a block from 1-12 grid columns wide, but floating the element right.
* `wrap-1` ... `wrap-12` - sizes a wrap from one grid column through to 12 with a default left float
* `rwrap-1` ... `rwrap-12` - sizes a wrap from 1-12 grid columns wide, but floating the element right.
* `unbleed` - layout block reclaims its own padding as margin, thus allowing for a content-width border.
* `hunbleed` - padding to margin reclaimation horizontally only
* `vunbleed` - padding to margin reclaimation vertically only
* `flush` - for full width blocks, just like a bleed but also claims the 10-pixel padding created by the parent `.page` wrapper. This allows for a full-width layout block that stretches flush from left to right including the guttering.
* `hflush` - reclaims all the horizontal space
* `vflush` - reclaims all the vertical space.



