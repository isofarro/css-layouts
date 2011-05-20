
A grid layout with balanced margins and paddings. This avoids the first/last, alpha/omega rubbish that pollutes other grid layout systems on the web. This one is based on a 12-column grid of 70 pixels each with a 10 pixel gutter (made up of 5 pixels margin around each block).

A layout block is a child of the `.page` container, and has a `span-X` where X is the number of grid-columns the layout block spans.

The `.page` wrapper contains a 5 pixel padding, and each layout block itself a 5 pixel margin. This creates the required 10 pixel guttering between layout blocks.

In situations where a layout block needs a background colour applied that bleeds into the gutter, the set of `.bleed`, `.hbleed` and `.vbleed` classes swap a layout block's 5 pixel margins out for 5 pixel padding, so that the background colour region is bleeding consistently into the gutter horizontally, vertically or both. (If all layout blocks had the `.bleed` class that would mean the guttering between columns is entirely done through the layout blocks' padding).

The `.flush`, `.hflush` and `.vflush` classes goes one step further than `.bleed` on full-width layout blocks . It grabs the padding of the containing `.page` as it's own padding too. This is useful for a full-width background-colour header that stretches the entire width of the `.page` container, including all the guttering.

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
* `bleed` - layout block reclaims its own margin as padding, thus allowing consistent background colour bleeding into the surrounding gutters.
* `hbleed` - margin to padding reclaimation horizontally only
* `vbleed` - margin to padding reclaimation vertically only
* `flush` - for full width blocks, just like a bleed but also claims the 5-pixel padding created by the parent `.page` wrapper. This allows for a full-width layout block that stretches flush from left to right including the guttering.
* `hflush` - reclaims all the horizontal space
* `vflush` - reclaims all the vertical space.



