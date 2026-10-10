# Hover effects research

Documentation for the hover effects lab. Saved 10 October 2026.

This file is the full research report on hover effects that can still be added. It also lists the 42 cards already in the lab, so a later pass can tell a new idea from one that already ships.

The lab is one page of hover cards. Each card plays an effect on a logo image or on a letter-by-letter headline, then returns to rest when the pointer leaves. The two families are Canvas 2D and GSAP. Shared knobs are radius and strength. GSAP loads from a CDN. A new effect should stay inside that setup.

Open the lab: [natasuu.github.io/effects-lab](https://natasuu.github.io/effects-lab/)

## Already in the lab

These 42 cards are built. The research below treats a look-alike as already done.

### Canvas

| Effect | What it does |
| --- | --- |
| Pixel burst | The artwork becomes thousands of pixels that scatter and reform. |
| Jelly | The surface squashes under the cursor and wobbles back. |
| Magnetic | Pieces lean toward the cursor, grow a little, and tilt. |
| Liquid ripple | A water simulation. The cursor drops waves that bend the picture. |
| Shatter | The artwork breaks into angular shards that spin away and snap back. |
| Glitch | Horizontal slices slip sideways with a cyan and magenta fringe. |
| Halftone | The artwork turns into swelling print dots around the cursor. |
| Scatter | Each piece is a rigid object. The cursor bats them away and they bounce home. |
| Sand | Pixels near the cursor crumble and fall. Leave, and they float back up. |
| Swirl | The area under the cursor twists like water down a drain, then unwinds. |
| Lens | A springy magnifying glass follows the cursor and pops open. |
| Wave | A sine wave travels through the artwork near the cursor. |
| Pixelate | A round window turns into chunky retro blocks. |
| Highlighter | A lime brush paints behind the artwork and fades. |
| ASCII | The artwork turns into flickering text characters around the cursor. |
| 3D tilt | Each piece turns in perspective to face the cursor. |
| Dissolve | Noise eats the artwork away around the cursor with a glowing edge, then it regrows. |
| Black hole | Pixels get sucked toward the cursor and orbit it. Leave, and they fly home. |
| Echo | Pieces chase the cursor with overshoot and leave ghost copies behind them. |
| Focus | Everything blurs except a sharp spotlight under the cursor. |
| Filings | Little needles swing round to point at the cursor. |
| Bulge | A fisheye bubble pushes the artwork outward under the cursor. |
| Pinch | The artwork gets sucked into a point under the cursor. |
| Glow | Pieces near the cursor light up with a colour-cycling halo. |
| Pluck | Rows act like guitar strings and twang when the cursor crosses them. |
| Confetti | Shards turn into flat party colours as they fly. |
| Melt | Columns stretch downwards and fade, like paint running. |
| Spotlight | A circle opens and the artwork flips to lime inside it. |
| Drop | Pieces get knocked loose, fall, and bounce. Leave, and they hop back. |
| Dock zoom | Pieces grow like macOS dock icons and push their neighbours aside. |
| VHS | Scanlines tear sideways. The tear follows the cursor. |
| Duotone | A navy and lime reprint eats outward from the cursor. |

### GSAP

| Effect | What it does |
| --- | --- |
| GSAP elastic | Pieces pop toward you with an elastic ease. |
| GSAP explode | A timeline flings every piece out, then elastics them home on leave. |
| GSAP scramble | Pieces flicker and jitter, then lock back. Works on letters too. |
| GSAP 3D flip | Pieces tip in perspective toward the cursor. |
| GSAP wiggle | Pieces shiver the whole time the cursor is over them. |
| GSAP inertia | Pieces are thrown away from the cursor, then slide and settle. |
| GSAP swap | Pieces trade places, then walk back home. |
| GSAP orbit | Pieces circle the cursor, then ease home. |
| GSAP cascade | Pieces drop in with a stagger, like a stacked title. |
| GSAP smear | Velocity skews the pieces, like a fast pan. |

## Twenty-six effects still earn a card

The lab can still add **twenty-six** hover effects. **Twelve** play on a logo and on a letter-by-letter headline, **ten** should be built for the headline only, and **four** should be built for the logo only. Each one can run in Canvas 2D or GSAP, disturb the artwork while the pointer is inside the card, and return to rest on leave.

The shared radius does real work on the Canvas lenses: a rim-refraction droplet, a chromatic rim, a Bayer matrix, a wet smudge, a cross-stitch sew-in, rising ink smoke, slat blinds, an opaque-run pixel sort, and a hole that reveals a second layer. GSAP’s leftover work is structure the ten shipped tweens never touch: a split-flap hinge, baseline tracking, a roll onto a second face, a scribble that draws and undraws, letters moving onto a circle, a word-shaped marquee, a diagonal crack, a masked letter wipe, and a corner flap. Two follow behaviors are still free, an overshoot with no ghost copies and a lagged swing with in-plane rotation, plus a flat color that tracks distance.

Scale, shake, a circle growing from the pointer, a torn RGB slice, letters falling to a floor, and strips flipping over are already in the lab under other names.

Family is the one that can do the effect without a new renderer. Subject is where the fidget stays recognizable. The last column is the shipped card a later pass will reach for, and the reason this effect is a different motion.

| Effect | Family | Subject | What separates it from the shipped cards |
| --- | --- | --- | --- |
| Rim-refraction glass | Canvas 2D | Both; logo stronger. On type, keep the droplet under about one em | Lens magnifies uniformly. Bulge pushes pieces outward. Here the sample bend is strongest at the rim and the center stays on the true artwork |
| Chromatic rim lens | Canvas 2D | Both | Glitch slips full-width slices. This never moves a row. Red, green, and blue separate along the radius and lock together at the center |
| Bayer dither lens | Canvas 2D | Both | Halftone dots swell with darkness. Pixelate averages blocks. Duotone remaps two inks. Bayer is a fixed threshold matrix |
| Smudge | Canvas 2D | Both | Highlighter paints a flat accent behind the art. GSAP smear skews pieces by velocity. Smudge copies pixels along the stroke, then fades a clean buffer back |
| Cross-stitch | Canvas 2D | Both, at 3–6 px cells | The mark is two crossing stitches in a thread color, not a halftone dot, a pixel block, or an ASCII character |
| Ink smoke | Canvas 2D | Both | The bitmap stays put. Sand, Melt, and Pixel burst remove or move the artwork. This is rising puffs, not the shader warp awarded as smoke |
| Slat blinds | Canvas 2D | Both | Each strip squashes toward its own center line. VHS tears sideways, Wave is a traveling sine, Pluck is independent strings, and a 3D slat flip is the lab’s 3D flip |
| Opaque-run pixel sort | Canvas 2D | Both, and only runs that are already ink | Glitch shifts, Melt stretches, VHS tears. Sort reorders a short band by brightness and must stop at transparent gaps |
| Pencil sketch | Canvas 2D | Headline. A flat two-color logo goes blank | Grayscale, invert, blur, color-dodge inside the radius. ASCII, Focus, and Duotone do not draw graphite |
| Voronoi mosaic | Canvas 2D | Logo. Fine type disappears once a cell is wider than a stroke | Cells are nearest-seed regions with a lead line, not axis-aligned Pixelate blocks, and nothing spins away as in Shatter |
| Metaball goop | Canvas 2D | Logo. Fine type merges into one puddle | Blobs fuse where a scalar field passes 1, then separate home. Pixel burst does not merge, Black hole orbits, Sand falls to a floor, Jelly wobbles a surface |
| Corner flap | GSAP | Logo. A one-line headline only curls a corner | A corner lifts, a shadow sits in the crease, the underside is a mirrored copy. Bulge, Wave, and 3D tilt do not peel |
| Traveling sheen | Canvas 2D | Logo | One translucent band at about 45° crosses the mark once and can be clipped to its alpha. Spotlight, Glow, and Highlighter stay with the pointer or bloom in place |
| Split-flap hinge | GSAP | Headline | The letter hinges on its own midline, clipped, with a shade when the flap is edge-on, same character on both sides. 3D flip aims at the pointer. Scramble rolls a charset. Cascade drops |
| Baseline tracking | GSAP | Headline | Letters move apart on the line and stay the same height. Explode throws them on random vectors. Dock zoom scales neighbors |
| Second-face roll | GSAP | Headline | The word rolls back on its top edge and a second copy, waiting underneath, comes up in another color. 3D flip tracks the pointer and has no parked back face |
| Scribble underline | GSAP | Headline | One hand-drawn stroke draws on enter and undraws on leave. Highlighter is a brush that follows the pointer and fades |
| Circular type | GSAP | Headline | Whole letters move from the baseline onto a circle or arc and rotate to the tangent, then return. Wave is a sine through pixels. Orbit circles the cursor |
| Clipped marquee | GSAP | Headline | A repeated copy of the word scrolls inside a window the width of the word, then settles to one copy. Smear is a velocity skew. Cascade is a drop-in |
| Diagonal crack | GSAP | Headline | The word is cut once, corner to corner, and the two pieces nudge apart and recolor. Glitch uses random bands and a cyan/magenta fringe |
| Masked letter wipe | GSAP | Headline | Each letter slides through an overflow clip. Cascade uses the same direction with `bounce.out` and no clip, so the type never hides behind a line box |
| Spring sag | Canvas 2D | Headline, and only with a spring strong enough that letters never land | Drop knocks pieces loose, drops them to a floor, and bounces them home. Here gravity, a pointer push, and a spring leave the word legible and restless |
| Overshoot follow | GSAP | Both | Pieces chase a small offset toward the pointer and pass that target before settling. Echo leaves ghost copies. Orbit is circular. Elastic pop is scale |
| Distance color | GSAP | Both | Each letter or tile interpolates a flat fill by distance inside the radius. Duotone reprints pixels in two inks. Spotlight is a circle of recolored artwork. Glow is a halo |
| Lagged swing | GSAP | Both | `x`, `y`, and in-plane rotation lag the pointer, and CSS brightness rises, then all four return. Smear writes `skewX`. 3D flip uses `rotationX` / `rotationY`. Glow is a canvas halo |
| X-ray hole | Canvas 2D | Both. Strongest when the hole shows a second layer | Spotlight opens a circle and recolors the same pixels. Duotone eats a two-ink reprint outward. The hole deletes pixels |

## Canvas: a rim, a matrix, and a thread

The Canvas cards worth building first are the ones that already match the lab’s two knobs. Radius is the disc, the brush, the spawn field, or the band. Strength is the second number the sources actually publish: rim offset, refraction factor, Bayer level count, stamp alpha, stitch-cell size, puff rate, how close a slat’s `scaleY` gets to closed, or how wide a brightness window is.

### Rim-refraction glass

Arcaweb’s droplet is the glass algorithm in Canvas 2D. For each pixel, a normalized distance from the rounded edge feeds `f = 1 + k * (1 - norm)^2`, and the sample is `center + (pixel - center) * f`. Negative `k` around `-0.3` is their convex example. The center, where the norm is 1, is unbent. A white rim is painted from that same norm. A droplet the size of the card collapses into Lens, and letter counters pinch shut, so the droplet stays smaller than the mark and the card keeps untouched artwork around it.

Source: [Arcaweb](https://www.arcaweb.ch/en/recreate-liquid-glass-effect-html-canvas)

### Chromatic rim lens

This is the radial cousin of that droplet. A full-frame channel slide replaces one channel with the same channel some pixels to the right across the whole image, which on a card reads as Glitch without the slices. The missing fidget samples red, green, and blue at three strengths along the line from the lens center, with the offset scaled by distance so the middle stays clean. liquidGL describes the same concentration: aberration disperses the red and blue channels either side of the refraction vector and vanishes at the flat centre. Two to six pixels of rim offset is the useful strength. Past that, a small logo turns to mud and serifs double.

Glass and the chromatic rim can share a disc. They should still be two cards, because one bends the sample and the other splits channels, and strength means `k` in one and a pixel offset in the other.

Sources: [lqt0223 gist](https://gist.github.com/lqt0223/8a258b68ae1c032fa1fb1e26c4965e8d), [liquidGL](https://github.com/naughtyduk/liquidGL)

### Bayer dither lens

A tiled matrix, indexed by `x mod n` and `y mod n`, turns intermediate tones into a stable dot pattern. Szabados’s multi-level form keeps brand color: with `c` grey levels, each channel is quantized after the matrix offset is added. Strength is the level count, 2 for a harsh black-and-white and 4–8 to keep the mark. An 8×8 cell bigger than a small logo destroys it, so logos use 4×4. Floyd–Steinberg and Atkinson smear error into neighboring pixels and leak dots into letter counters, so the card should stay ordered Bayer.

The 2025–2026 “retro dither” lens is a shader. The Canvas port is the still matrix inside the radius, feathered back to the original. Awarded plasma-dither hovers are fluid simulations and are a different effect.

Sources: [Bayer Dithering, 2022](https://spencerszabados.github.io/blog/2022/bayer-dithering/), [javaspring.net](https://www.javaspring.net/blog/monochrome-dithering-in-javascript-bayer-atkinson-floyd-steinberg/), [Awwwards, Outsource Consultants](https://www.awwwards.com/inspiration/interactive-dither-effect-outsource-consultants-inc)

### Smudge, stitch, smoke, blinds, and sort

These survive both subjects if a clean buffer and an alpha test are mandatory.

- **Smudge.** The paint demos are destructive. The lab version keeps an untouched bitmap, stamps a feathered patch along the pointer at partial alpha, and on leave fades the live buffer home. Sources: [Simple Paint Demo](https://math.hws.edu/graphicsbook/demos/c2/SimplePaintDemo.html), [smudge brush](https://stackoverflow.com/questions/28197378/html5-canvas-javascript-smudge-brush-tool)
- **Cross-stitch.** Downsample, quantize opaque cells to a thread color, draw an X, and sew cells in across the radius. The pipeline sources are pattern tools, not hovers. Source: [PhotoToPattern](https://dev.to/wei_zhu_aa04d872270a4135c/how-i-turned-photos-into-printable-cross-stitch-patterns-in-the-browser-2ma7)
- **Ink smoke.** Soft sprites spawn on opaque pixels, with an upward force and alpha tied to life. The source pixel stays. Source: [Middlebury, fall 2024](https://www.cs.middlebury.edu/~candrews/classes/cs467-f24/tutorials/tutorial06-smoke)
- **Slat blinds.** Cut the bitmap with the nine-argument `drawImage` and scale each band toward its center. The famous venetian versions rotate strips in 3D to a second image. That rotation is 3D flip. The Canvas card only squashes, and `scaleY` should clamp near 0.15 so a word does not vanish. Source: [The New Code](https://thenewcode.com/776/3d-venetian-blind-image-transition-in-pure-css)
- **Opaque-run pixel sort.** Reorder luminance inside a short band and end a run when alpha drops, or a letter’s stem gets painted across the counter. Source: [Emergent Mind](https://www.emergentmind.com/visualizations/pixel-sorting)

### One subject only

- **Pencil sketch.** Grayscale, an inverted blur, and color-dodge, `base / (1 - blend / 255)`, masked to the radius. Without internal edges a flat logo goes white. Headline only. Source: [JsonKit](https://jsokit.com/blog/posts/image-to-sketch-gaussian-blur-and-color-dodge-blending-with-canvas/)
- **Voronoi mosaic.** Each cell is the average of the opaque pixels nearest a seed. Darken the border between the nearest and second-nearest seed. Fine type disappears once a cell is wider than a stroke. Logo only. Source: [Lumitree](https://lumitree.art/blog/voronoi-diagram)
- **Metaball goop.** Sum `radius² / distance²` and paint where the sum passes 1. Chunky logos fuse and separate. Fine type becomes one puddle. Source: [slicker.me](https://slicker.me/javascript/metaballs/metaballs-tutorial.htm)
- **Traveling sheen.** Apollo’s sheen is a translucent slab, rotated about 45°, traveling from above the picture to below it, clipped to the mark’s alpha. Logo only. Source: [Codrops set 2](https://github.com/codrops/HoverEffectIdeas/blob/master/css/set2.css)

Posterize, the flat quantization with the Bayer matrix removed, does not earn its own card. On a brand logo that is already a few flat colors, the only motion is a jagged anti-aliased edge, and Bayer already owns quantization.

## Headlines: hinge, track, and a second face

The headline cards are GSAP because the lab’s headline is already one element per letter.

### Split-flap hinge

vawe.dev’s flap is a resolve that rolls through other characters, and that roll is the lab’s scramble. The hinge is the part to build. Each glyph is four layers, a tile about 0.72em by 1.1em, perspective 3em, the top half rotating shut on `transform-origin: 50% 100%` and the bottom half swinging up, 34 ms each way, a shade reaching 0.6 opacity when the flap is edge-on, and a 0.016em split line. Rotating the whole glyph keeps it one piece. `rotateX` without perspective only squashes, and there is no shade. On enter, flap the current character once. On leave, flap back. Do not cycle a charset.

Source: [vawe](https://vawe.dev/moves/flap-resolve)

### Baseline tracking

CodeFronts eases `letter-spacing` from `0.02em` to `0.35em` in about 350 ms. On the lab’s per-letter elements, GSAP moves each letter’s `x` to `(index - center) * gap` and back to 0. No rotation.

Proximity `wght` and `wdth` are real and well documented, and they are the wrong family for this lab. The effect is invisible without a variable font. A `wght` change has no honest transform fallback, and `scaleY` is dock zoom. A `wdth` axis also reflows the line. The tracking card is the fallback to build.

Sources: [CodeFronts](https://codefronts.com/motion/css-hover-effects/css-letter-spacing-expand-hover-effect/), [magnetType](https://github.com/Liiift-Studio/MagnetType)

### Second-face roll

Hakim El Hattab’s rolling link, as shipped in Codrops’ 2013 component: the word rotates on its top edge to `rotateX(90deg)` and a second copy that rested at `rotateX(-90deg)` arrives in another color.

Source: [Creative Link Effects](https://github.com/codrops/CreativeLinkEffects/blob/master/css/component.css)

### Scribble underline

The May 2025 DrawSVG demo draws a hand-drawn stroke from `"0%"` to `"100%"` in 0.5 s on enter and `"100% 100%"` on leave. DrawSVG is free with GSAP 3.13. The core fallback is `stroke-dasharray` plus `stroke-dashoffset` on a path under the word, not along the glyph.

Source: [Codrops, 14 May 2025](https://tympanus.net/codrops/2025/05/14/from-splittext-to-morphsvg-5-creative-demos-using-free-gsap-plugins/)

### Masked letter wipe

The same article’s SplitText `mask: "lines"` idea, rebound from the published click to enter and leave, with a hand-built overflow wrapper so the page does not need the plugin. Each letter slides through the clip. Cascade uses the same direction with bounce and no clip, so the type never hides.

### Diagonal crack

Urpi cuts the word once, corner to corner: two polygons, one `(0,0)-(width,0)-(width,height)` and the other `(0,0)-(0,height)-(width,height)`, nudged by a few pixels in opposite directions. The published offset is about 4 px and 1 px, so strength has to scale it or the card looks like a flicker.

Source: [Text Styles](https://github.com/codrops/TextStylesHoverEffects/blob/master/index.html)

### Circular type

Codrops’ circular SVG text, 3 March 2021, is an intro, not a hover. The lab version tweens whole letters from the baseline onto a circle or arc, rotates them to the tangent, then returns them. Wave is a sine through pixels. Orbit circles the cursor.

Source: [Codrops](https://tympanus.net/codrops/2021/03/03/circular-svg-text-animation/)

### Clipped marquee

Awwwards files marquee-on-hover as its own element type and confirms enter and mouseout. The pages do not describe a clip inside the letterforms, so the window-the-width-of-the-word is this lab’s shaping of that pattern. A repeated copy scrolls inside that window, then settles to one copy.

Source: [Awwwards](https://www.awwwards.com/inspiration/scrolling-marquee-text-on-hover)

### Spring sag

Edgeless Lab gives each letter gravity, an inverse-square pointer push, a spring home, and circle collision at restitution 0.7. The spring is what keeps the word a word. Pretext’s gravity letters and Matter.js drops are Drop. If the spring is weak, this card is Drop too.

Source: [Edgeless Lab](https://edgelesslab.com/blog/kinetic-type-physics/)

### Corner flap

The logo-side GSAP card. GSAP Vault’s sticker peel runs on GSAP core: a flap, a reflection matrix, `transform-origin: 0 0`, and a drop shadow. Canvas UI’s cylindrical peel is WebGL and a new renderer. curl.js can curl an image in Canvas 2D. The card to build is the GSAP flap. It loses the cylinder, the lip highlight, and a true backside, and it still reads as a peel on a square mark. A one-line headline only curls a corner.

Sources: [GSAP Vault](https://gsapvault.com/effects/sticker-peel), [Peel](https://canvasui.dev/docs/components/peel), [curl.js](http://www.netzgesta.de/curl/)

## Follow and color

Three GSAP motions look close to cards that already follow the pointer. They stay new if the property list is guarded.

### Overshoot follow

`gsap.quickTo` with an ease that passes the target. The official follower uses `power3`, which settles without overshoot. A May 2025 drag thread uses `elastic.out` for a return that springs past rest. Putting that ease on `x` and `y`, and leaving scale alone, is the missing combination. Leave sends every piece to 0. Echo is the card that would be rebuilt if the pieces also left copies behind.

Sources: [quickTo](https://gsap.com/docs/v3/GSAP/gsap.quickTo()/), [GSAP forum, 26 May 2025](https://gsap.com/community/forums/topic/44625-need-the-characters-spring-back-to-their-original-position-after-dragging-using-draggable-and-inertia-plug-in-not-working-need-help/)

### Lagged swing

Codrops, 1 July 2020, reveals a menu image and then, while the item is hovered, sets `x`, `y`, `rotation`, and `filter: brightness(...)` from lerped pointer values. The published subject is a photo beside menu text. The same four properties on each letter, or on a logo treated as one piece, are the card. Rotation here is in-plane. The moment it becomes `rotationX` and `rotationY` aimed at the pointer, it is 3D flip. The moment the horizontal component is `skewX` from velocity, it is smear.

Source: [Codrops](https://tympanus.net/codrops/2020/07/01/creating-a-menu-image-animation-on-hover/)

### Distance color

From the 14 May 2025 dot grid. On move, `t = max(0, 1 - dist / threshold)` and `gsap.utils.interpolate` writes a flat `color` or `backgroundColor`. Past the threshold the piece is the base color again, so leaving restores it. The lab’s radius is that threshold. The same article’s inertia push and click shockwave should be dropped. Those are already close to GSAP inertia.

Source: [Codrops, 14 May 2025](https://tympanus.net/codrops/2025/05/14/from-splittext-to-morphsvg-5-creative-demos-using-free-gsap-plugins/)

### X-ray hole

The Canvas companion to distance color. Two layers, a radial mask or `destination-out` circle spring-following the pointer, and a second string or a second-color mark underneath. shadcn.io cites stiffness 250 and damping 30. If the revealed art is the same pixels recolored, the card is Spotlight and should not be built.

Source: [Xray Text](https://www.shadcn.io/text/xray-text)

## Considered, and set aside

Most famous names in the catalogs are a shipped card.

| What people call it | What the lab already has | Source |
| --- | --- | --- |
| Grow, Push, Pulse, and the April 2026 “lift” | GSAP elastic, Dock zoom | [hover.css](https://ianlunn.github.io/Hover/) |
| Buzz, wobble, Asiri’s jolting grid | GSAP wiggle | [hover.css](https://ianlunn.github.io/Hover/) |
| A 4° rotate, roundup “tilt” | 3D tilt | [hover.css](https://ianlunn.github.io/Hover/) |
| A held `skew(-10deg)`, Alena Orlova’s skewed grid (13 Sep 2023) | GSAP smear | [Codrops](https://tympanus.net/codrops/2023/09/13/grid-item-hover-effect/) |
| Radial Out, Rectangle Out, CodeFronts iris | Spotlight | [hover.css](https://ianlunn.github.io/Hover/) |
| hover.css Glow | Glow | [hover.css](https://ianlunn.github.io/Hover/) |
| “Fall down,” staggered letter rise, “split text” | Drop, GSAP cascade | [hover.css](https://ianlunn.github.io/Hover/) |
| Nukun’s `rotateY(180deg)`, Yaku’s full turn, 3D venetian blinds | 3D flip | [The New Code](https://thenewcode.com/776/3d-venetian-blind-image-transition-in-pure-css) |
| Terminal shuffle, Quai’s `shuffleChars`, Brilliant Digital’s digit scramble | GSAP scramble, Glitch | [Awwwards](https://www.awwwards.com/inspiration/glitch-chromatic-aberration-404-with-digit-scramble-brilliant-digital-2) |
| Repetition layers, stacked scales | GSAP elastic | [hover.css](https://ianlunn.github.io/Hover/) |
| nxworld blur | Focus | hover.css roundups |
| Magnetic buttons, October 2025 shader ripples | Magnetic, Liquid ripple | [hover.css](https://ianlunn.github.io/Hover/) |
| Evervault’s radial gradient mask, 17 May 2023 | Spotlight | [Codrops](https://tympanus.net/codrops/2023/05/17/recreating-the-gradient-mask-hover-effect-from-evervault/) |
| Robin Payot’s June 2023 WebGL bulge | Bulge | [Codrops](https://tympanus.net/codrops/2023/06/28/creating-a-bulge-distortion-effect-with-webgl/) |
| 18 Jan 2026 canvas “liquid distortion” | Bulge plus Jelly | [freefrontend](https://freefrontend.com/code/interactive-canvas-liquid-image-distortion-2026-01-18/) |
| Full-frame chromatic shift | Glitch | [lqt0223 gist](https://gist.github.com/lqt0223/8a258b68ae1c032fa1fb1e26c4965e8d) |
| Repelling image particles that spring home | Scatter | canvas particle demos |
| Pointillism | Halftone | canvas image demos |
| Quai Network alternating clip slices, 21 Jun 2023 | Slat blinds, plus scramble for the character shuffle | [Codrops](https://tympanus.net/codrops/2023/06/21/coding-the-sliced-image-hover-effect-from-quai-network/) |
| Page-scale gooey cursor, 7 Jun 2023, and the 2020 gooey menu | Jelly. Metaball goop is the card-local version of that fuse | SVG filter demos |
| Image trails, including the 2019 Three.js plane | Echo, once shrunk to one card | award-site cursor trails |
| Physics2D letters that leave the viewport | Shatter, GSAP explode | GSAP physics demos |
| Elastic drag-home | A press. The lab’s gesture is leave | GSAP forum |
| MorphSVG and MotionPath along a glyph | Needs an SVG path. Raster tiles and HTML letters do not have one | [Codrops, 31 Jan 2023](https://tympanus.net/codrops/2023/01/31/bringing-letters-to-life-coding-a-kinetic-svg-typography-animation/) |
| Glyph stroke-draw, inner-stroke fill, a stitch along a logo outline | A PNG has no path. Tracing the bitmap invents a different mark | [Codrops, 31 Jan 2023](https://tympanus.net/codrops/2023/01/31/bringing-letters-to-life-coding-a-kinetic-svg-typography-animation/) |
| Live liquid glass, Dorian Lods 2025, liquidGL, Apple Liquid Glass (June 2025) | GPU or live-page lenses. The card-local sample remap is rim-refraction glass | [liquidGL](https://github.com/naughtyduk/liquidGL) |
| PANAMÆRA smoke cursor, Codapress dither plasma | Shaders. The ports are ink smoke and the still Bayer matrix | Awwwards |
| Canvas UI peel, June 2026 Three.js paint reveal, LO2S 2025 logo shaders | A new WebGL family | [Peel](https://canvasui.dev/docs/components/peel) |
| Verlet cloth | On a small logo it looks like Jelly | [Cylian](https://cylian.org/canvas/cloth/) |
| Slit-scan | A still logo reproduces itself. Sparse letters write empty strips | [thewhodidthis](https://thewhodidthis.com/slit-scan-thing/) |
| Kinetic rows, Codrops 29 May 2024 | Read as Wave. Lagged swing already owns a delayed `x` | Codrops |
| FLIP flex | The published pen grows a cell inside a grid of neighbors. One lab card has no neighbors to reflow | [GreenSock pen](https://codepen.io/GreenSock/pen/jEbpKYG) |
| Zoom inside a crop, a 5 px float, grayscale, a growing rectangular border | Real, missing, and too plain to spend a card on | CSS hover catalogs |

## How to use this later

The lab has finished the transform vocabulary. Scale, skew, spin, throw, orbit, and flip are shipped, so a new GSAP card earns its place only when the motion is a hinge, a clip, a stroke under the word, a second face, or a flat fill by distance.

The Canvas work that is still open is local resampling: touch the rectangle around the pointer, ignore pixels below an alpha cutoff, and tie the smallest feature (Bayer cell, stitch, Voronoi seed, metaball radius, channel offset) to strength so it stays smaller than the logo and the letter stroke. Glass and the chromatic rim are the 2025–2026 looks that survive that test without WebGL.

Anything pitched later as liquid, glitch, or slices should be checked against Bulge, Jelly, Glitch, and the slat card before it is allowed a tile.

Sources for this pass: hover.css, Codrops, GSAP docs and the GreenSock forum, Awwwards, and Canvas 2D tutorials, gathered 10 October 2026. Working notes from the same pass sit in `research_notes/Unbuilt hover effect ideas/`.
