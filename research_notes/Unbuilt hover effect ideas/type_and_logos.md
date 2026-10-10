# Type and logo pointer effects missing from the lab

Scope: pointer effects designed for letters, words, or brand marks, checked against the lab as of 10 October 2026. The lab already has letter scramble, elastic pop, 3D flip, wiggle, orbit, cascade drop-in, velocity smear, swap, explode, magnetic lean, dock zoom, jelly, sine-flag wave, pluck-as-strings, glitch slices, ASCII replacement, spotlight color flip, duotone, glow, focus blur, melt, drop, shatter, confetti, filings, black hole, echo, bulge, pinch, pixelate, highlighter, and VHS tear. Those are rejected below even when a source exists.

Lab fit used throughout: one card, vanilla JS, Canvas 2D or GSAP, effect reverses when the pointer leaves. No variable-font library. Headline mode is one element per letter. Logos mode is a client mark as an image.

Fourteen candidates are sourced below (1–9 are type-first, 10–14 are mark-first). Each says what the pointer does, which subject it prefers, whether a variable axis is required, and why it is not a duplicate.

## What kinetic-type hovers are common on 2022–2026 award sites and type-foundry experiments?

### Takeaway

Pointer-driven variable axes (weight, width, slant) are well documented in 2024–2026 component labs, not on the Dinamo specimen pages checked here. Award-site collections confirm marquee-on-hover and SVG text drawing; the mechanical, circular, palette, and chromatic treatments come from Codrops, CSS-Tricks, and individual write-ups. A free-floating “letters fly away from the cursor” demo is not a new effect for this lab.

### Cited Findings

**1. Proximity weight (`wght`)**

- The pointer makes the nearest letters heavier. Rest weight returns as the pointer moves away, and the whole word returns to rest on leave. Radius is local (NedDev uses 140px and a smoothstep falloff; Fancy Components’ proximity component defaults to 50px with linear, exponential, or gaussian falloff). — [NedDev Lab, Cursor Proximity Weight](https://neddev.com/en/lab/text-animations/cursor-proximity-weight/); [Fancy Components, Variable Font and Cursor](https://www.fancycomponents.dev/docs/components/text/variable-font-and-cursor); [Daniel Pethő, Variable Font Cursor Proximity](https://21st.dev/@danielpetho/components/variable-font-cursor-proximity.md); [Dirck Mulder, Variable Font Proximity](https://www.dirckmulder.com/blog/variable-proximity); [Liiift Studio, magnetType](https://github.com/Liiift-Studio/MagnetType)
- NedDev’s published snippet does not set `font-variation-settings`. It steps `font-weight` from 400 to 900 in increments of 100, and tints a letter accent-orange when the falloff exceeds 0.6. The page says a variable font makes the same idea smooth. It attributes the idea to Fancy Components (MIT). — [NedDev Lab](https://neddev.com/en/lab/text-animations/cursor-proximity-weight/)
- magnetType states the effect is invisible without a variable font. A `wght`-only change does not change advance widths, so the line does not reflow. A `wdth` change does reflow. — [magnetType](https://github.com/Liiift-Studio/MagnetType)
- Dirck Mulder’s example interpolates `'wght' 100, 'wdth' 75` to `'wght' 900, 'wdth' 125` per character, with gaussian falloff, inside a `requestAnimationFrame` loop that writes `fontVariationSettings` and skips the write if the pointer has not moved. — [Dirck Mulder](https://www.dirckmulder.com/blog/variable-proximity)
- A March 2026 gist maps distance to `'wght'` from 100 to 900 on per-letter spans using Inter. — [Samuel Didier-Laurent gist](https://gist.github.com/frontalex/df70b8cec2fcb9841553b80d2868df33)
- Prefers a short headline. A bitmap logo has no glyphs and no axis.
- Axis: `wght`. A transform-only fallback does not exist. `scaleY` thickens the letter without changing stroke contrast or the glyph outline, so it reads as dock zoom, which the lab already has.
- Fit: neither Canvas nor GSAP is required. Per-letter DOM styles are the documented method. GSAP `quickTo` can ease the axis value. Canvas can only fake it by swapping pre-rendered weight sprites, which is a step look, not the axis.
- Not a duplicate: dock zoom scales pieces and pushes neighbours. This redraws the glyph at a heavier master. Magnetic lean rotates. Elastic pop is a scale overshoot.

**2. Proximity width (`wdth`) with a tracking fallback**

- The pointer makes nearby letters wider, or, without a variable font, increases the gap after each letter. On leave, width and spacing return. — [Dirck Mulder](https://www.dirckmulder.com/blog/variable-proximity); [magnetType](https://github.com/Liiift-Studio/MagnetType); [CodeFronts, letter-spacing expand](https://codefronts.com/motion/css-hover-effects/css-letter-spacing-expand-hover-effect/)
- CodeFronts documents a uniform hover, not a proximity field: `letter-spacing` from `0.02em` to `0.35em`, a collapse from `0.4em` back to `0.02em`, and one variant that also goes from `font-weight: 400` to `900`. Timing is about 350ms with `cubic-bezier(.4,0,.2,1)`. — [CodeFronts](https://codefronts.com/motion/css-hover-effects/css-letter-spacing-expand-hover-effect/)
- Prefers a headline. Tracking on a bitmap wordmark fails because the letters are one image.
- Axis: `wdth`, range in the Dirck Mulder example is 75 to 125. Fallback exists and is honest: animate per-letter `margin-right` or GSAP `letterSpacing`. `scaleX` is a worse fallback because it stretches the strokes. magnetType warns that `wdth` changes advance widths and the line reflows. — [magnetType](https://github.com/Liiift-Studio/MagnetType)
- Fit: GSAP for a uniform tracking tween (`letterSpacing`). Canvas 2D if each glyph is redrawn with a measured advance. DOM is enough for the proximity version.
- Not a duplicate: dock zoom changes scale, not advance width or spacing. The letters stay the same height.

**3. Card position mapped onto two axes**

- This is a different pointer mapping from proximity. Horizontal position in the card drives one axis from min to max. Vertical position drives a second axis. Fancy Components’ `fontVariationMapping` uses `name`, `min`, and `max` on `x` and `y`. The docs name `wght` and `slnt`. The whole run of text shares one setting. It is not a per-letter bulge. — [Fancy Components, Variable Font and Cursor](https://www.fancycomponents.dev/docs/components/text/variable-font-and-cursor)
- An older demo maps `wght` and `CASL` to mouse X/Y, and another mapping uses `wght` and `opsz` on Lunia D’Ambrosio’s Cantina. — [variable-font-axes-to-mouse-position](https://github.com/abodyammar/variable-font-axes-to-mouse-position)
- Prefers a headline. Useless on a bitmap logo.
- Axes: any two the font actually has. `slnt` has a real transform fallback (`skewX`). `wght` and `opsz` do not. `CASL` (casual) does not.
- Fit: DOM `font-variation-settings` from pointer position inside the card. GSAP can tween back to the rest values on leave. Canvas cannot interpolate masters.
- Not a duplicate: proximity weight is a local brush. This is one global setting for the whole word, driven by where the pointer sits in the card. It is not scramble, flip, or scale.

**4. Color palette per glyph**

- On hover, a COLR color font swaps palette. CSS-Tricks shows `font-palette` transitioning over 250ms on hover for the Google color fonts Honk and Nabla, using `@font-palette-values` with `base-palette`. Chromium can interpolate the palette. The same article says Safari and Edge treat `font-palette` animation as discrete. — [CSS-Tricks, `@font-palette-values`](https://css-tricks.com/almanac/rules/f/font-palette-values/); [CSS-Tricks, `font-palette`](https://css-tricks.com/almanac/properties/f/font-palette/)
- Prefers a headline set in a COLR font (Nabla or Honk are the fonts named in that article). A bitmap logo cannot take a font palette.
- Axis: none. This is a color font, not a weight axis. Fallback that does not need COLR: on enter, assign each letter a color from a fixed brand palette; on leave, return every letter to one color. That fallback is an implementation note, not a second sourced demo. NedDev only adds a single accent when weight falloff is high, which is not a palette. — [NedDev Lab](https://neddev.com/en/lab/text-animations/cursor-proximity-weight/)
- Fit: CSS transition on `font-palette` for the real effect. The span fallback is DOM color, optionally eased with GSAP. Canvas can fill each glyph in a palette color.
- Not a duplicate: spotlight flips the same artwork to one accent inside a circle. Duotone reprints the whole image in two inks from the cursor outward. A palette assigns a different ink to each glyph and restores the original ink on leave. No region, no threshold.

**5. Split-flap hinge, without a character roll**

- Each letter is a tile. The top half rotates shut on a horizontal hinge (`transform-origin: 50% 100%`, `rotateX` from 0 to -90deg) and the bottom half swings up (`transform-origin: 50% 0`). vawe.dev specifies four layers, a tile of 0.72em by 1.1em, `perspective: 3em`, 34ms fall plus 34ms rise, a shade that reaches 0.6 opacity when the flap is edge-on, and a 0.016em split line. — [vawe, flap-resolve](https://vawe.dev/moves/flap-resolve)
- The published vawe move is a resolve (a name or status locking in), and it rolls through other characters before landing. That roll is letter scramble, which the lab already has. The hinge itself is the part that is not in the lab. On enter, flap each current glyph once around its own hinge (same character on both sides, or a single blank-to-glyph flap). On leave, flap back. Do not cycle a charset.
- vawe states the failure mode explicitly: rotating the whole glyph is a card flip, not a split flap, because the glyph stays one piece, `rotateX` without perspective only squashes, and there is no shade. — [vawe](https://vawe.dev/moves/flap-resolve)
- Prefers a headline. A bitmap logo can flap as one tile, which loses the per-letter Solari read. Slicing the bitmap into a grid of flaps is possible but the hinges will not sit on glyph boundaries.
- No variable font. No transform fallback beyond the hinge itself; the effect is the hinge.
- Fit: GSAP `rotationX` on clipped halves. Canvas 2D can draw the two halves with a scaleY squash, which is the flat version vawe says fails. Prefer GSAP.
- Not a duplicate: the lab’s 3D flip and 3D tilt tip each piece toward the pointer on `rotationX` / `rotationY`. A split flap always hinges on the letter’s own midline, in one direction, with a clipped seam and a shade. Cascade is a Y drop with bounce, not a hinge.

**6. Circular text, then back to a line**

- Codrops (3 March 2021, Manoela Ilic) sets several lines of type on circular SVG paths and animates them as an intro, not as a hover. The article points at Amelia Bellamy-Royds for `<textPath>` construction, and at a 2019 Alpacka / Nathan Riley holding-page animation and Michael Crawford’s Spiral Scheduler as the references. Tags on the article include “circular” and “hover”, but the body describes an intro and a page transition. Demos: [demo 1](https://tympanus.net/Development/CircularTextEffect/), [demo 3](https://tympanus.net/Development/CircularTextEffect/index3.html). — [Codrops, Circular SVG Text Animation](https://tympanus.net/codrops/2021/03/03/circular-svg-text-animation/); [Amelia Bellamy-Royds, text paths](https://oreillymedia.github.io/Using_SVG/extras/ch07-textpaths.html)
- Lab adaptation, stated as an adaptation: on enter, move each letter from the straight headline onto a circle (or a single arc) and rotate it to the path tangent. On leave, tween back to the baseline. That reverse is not what the Codrops demos do.
- Prefers a short headline. A few words fit a circle. A bitmap logo cannot be reflowed letter by letter. Spinning the whole image is a different effect.
- No variable font. The placement is transforms (x, y, rotation) or SVG `<textPath>`. Canvas 2D can draw each glyph at `cos` / `sin` with the tangent as the rotation.
- Fit: GSAP for the to-circle and back-to-line tween. Canvas if the lab is already drawing glyphs. `<textPath>` is the construction Codrops uses, and it does not need a font library.
- Not a duplicate: the lab wave is a sine traveling through pixels “like a flag in wind.” Circular type moves whole letters onto a closed path and rotates each one to the tangent. It is not orbit (pieces circling the cursor) and not a scale.

**7. Marquee clipped to the word**

- Awwwards has a recurring “marquee on hover” element. Pages found: a generic “Scrolling Marquee Text on Hover” in the collection “Hovers, Cursors and Cute Interactions”; “Marquee animation on hover” credited to Juliet; “Lunchbox - Marquee text on hover button”; “Miranda Biondi - Marquee text mouseover events,” tagged text marquee, `onmouseover`, and `onmouseout`. The element pages fetched for this pass did not describe whether the ticker is a label strip or a clip inside the letterforms. — [Scrolling marquee](https://www.awwwards.com/inspiration/scrolling-marquee-text-on-hover); [Juliet](https://www.awwwards.com/inspiration/marquee-animation-on-hover); [Lunchbox](https://www.awwwards.com/inspiration/lunchbox-marquee-text-on-hover-button); [Miranda Biondi](https://www.awwwards.com/inspiration/miranda-biondi-text-marquee)
- Lab adaptation: on enter, duplicate the headline and translate it on a loop inside an overflow window the width of the word. On leave, stop the loop and tween back to one resting copy. That “inside the word” clip is the adaptation; the Awwwards pages confirm the hover-in / mouseout-out pattern, not the clip.
- Prefers a headline. A bitmap cannot ticker its own letters. It can be an alpha mask over a scrolling fill, which is a different effect and only works if the file has transparency.
- No variable font.
- Fit: GSAP `x` loop, paused and reversed on leave. Canvas can blit a repeated string. DOM overflow is the smallest version.
- Not a duplicate: nothing in the lab scrolls a repeated copy of the word through a fixed window. Smear is a velocity skew. Cascade is a drop-in.

**8. Spring sag (gravity that does not reach the floor)**

- Edgeless Lab treats each letter as a body with Verlet integration: constant downward gravity, an inverse-square push from the pointer, a spring back to the letter’s home in the word, and circle collision at restitution 0.7. The write-up says the spring is what keeps the word a word; without it the letters fall and scatter. The spring is tuned so the return takes seconds, not frames. The word stays “legible but restless.” — [Edgeless Lab, Kinetic Type Physics](https://edgelesslab.com/blog/kinetic-type-physics/)
- Prefers a headline. One bitmap treated as a single body only sags as a slab.
- No variable font. Do not add Matter.js. The Edgeless description is a few forces on points, which is vanilla Canvas.
- Fit: Canvas 2D. GSAP is a poor fit for forces applied every frame. On leave, zero the pointer force and let the springs finish, or tween the last stretch home if a spring would feel too slow for a card.
- Not a duplicate only if the springs are strong enough that letters droop and never land on a floor. The lab’s Drop knocks pieces loose, drops them to a floor, and bounces them home. If the spring is weak, this becomes Drop plus Scatter. Pretext’s gravity demo and niceunderground’s Matter.js “Pensieri” drop glyphs as rigid bodies and are the Drop family, not this candidate. — [Pretext, Gravity Letters](https://pretext.xergioalex.com/demos/gravity-letters/); [niceunderground/gravity](https://github.com/niceunderground/gravity)

**9. Chromatic letters (channel drift, no slices)**

- Three copies of the word (or of the mark) sit in red, green, and blue with `mix-blend-mode: screen`, so they read as one light mark when aligned. As the pointer approaches, the red copy drifts one way and the blue copy the other. On leave they line up again. shadcn.io describes spring-smoothed offsets, an intensity control, and an idle sine when there is no pointer. — [shadcn.io, Chromatic Text](https://www.shadcn.io/text/chromatic-text)
- The same stack works on a logo image. Coltography offsets five tinted copies of a logo (`mix-blend-mode: lighten`) and eases them back into alignment on hover, reversing the offsets when the pointer is gone. — [Coltography, additive colour logo](https://coltography.ca/creating-a-dynamic-logo-with-css-and-additive-color-mixing/)
- Prefers either subject. A headline can duplicate per glyph or as one string. A logo image is duplicated as a whole. Per-glyph drift needs live text or pre-split layers. A single bitmap can still drift as three channel copies.
- No variable font. The effect is translation of extra copies. Canvas 2D can draw the image three times and tint with `source-in`.
- Fit: GSAP on the copy offsets, reversed on leave. Canvas if the lab composites the card anyway.
- Not a duplicate: Glitch slips horizontal slices and adds a cyan/magenta fringe. VHS tears scanlines. Chromatic drift keeps every letter intact, moves whole channel copies along the pointer, and eases them back to one mark. No clip-path strips, no random jitter.

### Inferences

- “Common on award sites” is only fair for marquee-on-hover, which Awwwards files as its own element type, and for SVG stroke drawing, which Codrops and studio write-ups repeat. Variable-axis hovers are common in public component labs (Fancy Components, magnetType, NedDev, Dirck Mulder) and rare or absent on the foundry pages checked. Calling them an award-site trend would overclaim.
- A shallow arc (letters on a quadratic that bends toward the pointer, each rotated to the tangent) is the same machinery as candidate 6, with a smaller path. It is the baseline wave that is not a sine flag. It is listed as a variant of circular type, not as a fifteenth effect, because no separate hover demo of a cursor-sagged baseline was found.
- Fancy Components’ other component, Text Cursor Proximity, interpolates arbitrary CSS, including scale. Scale-by-distance is dock zoom. Do not port that component wholesale. — [Text Cursor Proximity](https://www.fancycomponents.dev/docs/components/text/text-cursor-proximity)

### Gaps

- Dinamo’s Font Gauntlet animates variable axes when you press play after uploading a font. It is not a pointer hover. The Darkroom page also describes a Gauge plugin that turns the cursor into an oval for measuring stroke width inside the Glyphs app, which is a design tool, not a site hover. — [Dinamo Darkroom](https://abcdinamo.com/darkroom)
- ABC Gravity is a 12-width headline family sold as one variable font (Robert Janes, Dinamo). The specimen does not show a pointer driving the width. — [ABC Gravity specimen PDF](https://abcdinamo.com/specimen/210331_Dinamo-ABC-Gravity_Specimen.pdf)
- ABC Whyte Inktrap’s ink traps are a drawing feature of the typeface, not an ink-bleed hover. — [Whyte specimen PDF](https://abcdinamo.com/specimen/Dinamo_Specimen_Whyte.pdf)
- No reliable 2022–2026 page was found for: ink bleed on hover, strings drawn between letter centers, letters tumbling around their own baseline as a hover, or a marquee whose video was available to confirm the clip. Godly’s logo library (`https://godly.design/logos`) is a gallery of marks, and this pass did not extract pointer behaviors from it.
- Awwwards pages titled “Hero Font and Cursor Interaction with Colorful Effects,” “Typographic hover effect” (Joey Maese / 10x17), “Interactive Hero Typography” (Visual Identity Studio), and “Typography With 3D Folding Effect” (Romain Granai, tagged scroll and WebGL) did not return a description of the motion. They are not used as evidence for a specific effect. 3D folding was not recommended because it is likely to collapse into the lab’s 3D flip, and the page did not confirm otherwise.
- Per-letter rotation around the baseline was not given its own candidate. vawe only describes whole-glyph `rotateX` as the wrong way to build a split flap. That is not a positive source for a hover.

## Which logo-mark interactions are common?

### Takeaway

The sourced mark interactions are all path effects: draw the outline, grow an inner stroke until the letter fills, or march a dashed stitch along the outline. A cursor-shaped hole that reveals a second layer is sourced for type and ports to a logo image. Stamp, emboss, counter-only fill, and “the pieces regroup into a different designed arrangement” were not found as primary hover demos.

### Cited Findings

**10. Stroke draw-on (monoline or logo outline)**

- Each path draws itself with `stroke-dashoffset`, then can undraw. Louis Hoebregts, Codrops, 31 January 2023, rebuilt the Orion Icon Library wordmark: a hairline / monoline font, one path per stroke, each path cloned in three colors (`#e97777`, `#ffc777`, `#fffad7`), GSAP timeline, `strokeDashoffset` from the path length to 0 over 1.2s with `power3.out`, 250ms between colors. He notes the reverse: animate offset toward `length * 2`, or reverse the path in Illustrator or Inkscape. The article says this cannot be done with a normal filled typeface, because each letter has to be one thick stroke. — [Codrops, kinetic SVG typography](https://tympanus.net/codrops/2023/01/31/bringing-letters-to-life-coding-a-kinetic-svg-typography-animation/)
- A logo-shaped version of the same draw is the usual outline trace. Manual `stroke-dashoffset` does not need the DrawSVG plugin. The May 2025 Codrops roundup treats DrawSVG as a free GSAP plugin for a scribble underline on hover; that underline is not this candidate, but it confirms the hover-in / reverse-on-leave pattern for a stroke. — [Codrops, 14 May 2025](https://tympanus.net/codrops/2025/05/14/from-splittext-to-morphsvg-5-creative-demos-using-free-gsap-plugins/)
- Prefers an SVG logo or a headline that has been converted to monoline paths. A bitmap has no path. An automatic trace will invent the wrong centerline and will weld thin joins.
- No variable font.
- Fit: GSAP on `strokeDashoffset`, reversed on leave. Canvas 2D can stroke a path with a dash offset, but only after the path exists.
- Not a duplicate: nothing in the lab draws a contour. Glitch, VHS, and highlighter do not follow the outline.

**11. Outlined to filled (inner stroke)**

- On hover, `stroke-width` animates from 0 to a value that covers the letter (16 in the demo) over 500ms, with a per-letter delay (0 / 200 / 400ms on the C, K, and N of the author’s mark). The stroke is clipped to the letter so it cannot spill past the outline. Christopher Kirk-Nielsen, 25 February 2023, uses a `<clipPath>` whose path is also `<use>`d, so the geometry exists once. `paint-order="stroke"` lets the fill sit above the stroke without a second copy. On leave the width returns to 0, so the letters go back to outline. He also shows the inverse, a mask that grows the stroke outward, and warns that each letter needs one shared mask or the strokes spill onto their neighbours. — [chriskirknielsen.com](https://chriskirknielsen.com/blog/animate-an-svg-inner-stroke/)
- Prefers an SVG wordmark or logo. This is the outlined-to-filled effect. It fills the body of the letter from the edges in. It does not specifically fill the counter (the hole of an O).
- No variable font. There is no transform fallback. A clip-wipe of a solid copy is a different effect.
- Fit: CSS transition is what the article uses. GSAP can tween `strokeWidth` and reverse it. Canvas would need a clip to the glyph and a growing stroke, which is more work for the same result.
- Not a duplicate: spotlight and duotone recolor pixels. This changes the amount of ink inside a vector outline, from hairline to solid, and reverses.

**12. Stitch along the outline**

- A dashed stroke is revealed by drawing a solid mask path, so the dashes appear to be laid down rather than sliding as one texture. Craig Roblewsky (Motion Tricks) duplicates the path, puts a solid white copy in a mask, and runs DrawSVG from 0 with `yoyo: true`. He also tweens `stroke-dasharray` (example: 24,24 to 8,12) while the mask draws, and notes MotionPath can pin an object to the tip. The published demo loops. The lab version is enter = draw, leave = reverse the mask offset. — [Motion Tricks, SVG dashed line](https://www.motiontricks.com/svg-dashed-line-animation/)
- A scroll snippet uses `stroke-dasharray="6 6"` and moves a needle group to `getPointAtLength` until a filled shape fades in. It is scroll, not hover, and the path in the snippet is a blob, not a logo. Useful only as a picture of “dashes read as stitches.” — [Scroll thread stitch](https://webdevpuneet.com/ui-snippets/scroll-thread-stitch-reveal/)
- Prefers an SVG logo outline. A headline works only after it is converted to paths. A bitmap has nothing to stitch.
- No variable font.
- Fit: GSAP. Manual dash offset matches candidate 10; the stitch is the same draw with a short dash and round caps. Canvas can dash a path if one exists.
- Not a duplicate: candidate 10 is a continuous stroke. Stitch is a broken dash that reads as thread, ideally with the dash phase held still while a mask reveals it, so the stitches do not crawl. Pluck is guitar-string displacement of rows, not a contour.

**13. Cursor hole (knockout), revealing a second layer**

- shadcn.io’s Xray Text stacks two strings. A `mask-image` radial gradient follows the pointer and punches a hole in the front string so the back string shows through. The hole is spring-smoothed (the page cites stiffness 250 and damping 30). The back string can be a different message. The hole closes when the pointer leaves. — [shadcn.io, Xray Text](https://www.shadcn.io/text/xray-text)
- CSS-Tricks documents the static construction: `mix-blend-mode` (`multiply`, `screen`, `darken`, `lighten`) or `background-clip: text`, or an SVG mask with black text on a white rect. That article is the knockout technique, not a cursor-following hole. — [CSS-Tricks, knockout text](https://css-tricks.com/css-techniques-and-effects-for-knockout-text/)
- Prefers a headline if the payoff is a second string. A logo image works as the front layer: the hole follows the pointer and shows the card, or a second-color mark, underneath. The second-color version is only worth building if the revealed art is not the same pixels recolored, because that is the lab’s spotlight.
- No variable font. Canvas `destination-out` for a soft circle is the bitmap version. GSAP or a spring on the hole position.
- Not a duplicate: Spotlight opens a navy circle and flips the same artwork to lime inside it. Duotone eats a two-ink reprint outward. The hole deletes pixels. What you see inside is another layer, and it is gone on leave.
- Rejected cousin: shadcn’s “Text Hover Effect” reveals a rainbow through a radial mask on the same SVG text, after an initial stroke draw. That radial recolor is spotlight. — [shadcn.io, Text Hover Effect](https://www.shadcn.io/text/text-hover-effect)

**14. Chromatic logo stack**

- Same mechanism as candidate 9, called out here because Coltography built it for a mark: several absolutely positioned logo images, `mix-blend-mode: lighten`, each with its own resting offset, eased to `top: 0` on hover over about 0.4s, and back to the offsets when not hovered. — [Coltography](https://coltography.ca/creating-a-dynamic-logo-with-css-and-additive-color-mixing/)
- Prefers a logo image. It is one of the few effects that is better on a bitmap than on live type, because the fringe appears on the silhouette rather than on a typeface’s contrast.
- No variable font. Transforms only.
- Fit: GSAP on the layer offsets. Canvas channel split if the source is one file rather than five pre-tinted exports.
- Not a duplicate: same distinction as candidate 9 versus Glitch and VHS. Listed once in the count; this entry is the logo-subject note for that effect.

### Inferences

- “Trace the outline,” “outlined to filled,” and “stitch” are one GSAP stroke toolkit with three dash and clip setups. They should be three cards, not one, because the read is different: a signature, a letter filling in, and embroidery.
- A mask reveal of a second color is only distinct from Spotlight when the mask is not a circle of recolor. The distinct versions that were actually sourced are Kirk-Nielsen’s inner stroke (ink amount) and the x-ray hole (a different layer). A horizontal wipe of a second fill, described at svg-animation.com, was not used as a candidate. The page reads as a generic tutorial and was not corroborated.
- “Pieces reassemble into a different arrangement” is only sourced as candidate 6 (a line becoming a circle and back). No sourced demo showed a wordmark breaking into a monogram, or a symbol regrouping into a second composition, and then reversing on leave.

### Gaps

- Fill-the-counter, as in the hole of an O or A filling while the stroke stays put, was not found as a hover. Inner stroke fills the body, not the counter.
- Stamp (a rotated impression with an ink texture) and emboss (a bevel whose light follows the pointer) had no reliable primary page in this pass.
- Awwwards “SVG mask hover microinteraction” on Erika Moreira’s portfolio, credited to Bruno Arizio, does not describe the mask. — [Awwwards element](https://www.awwwards.com/inspiration/svg-mask-hover-animation-erika-moreira-portfolio)
- Codrops’ gooey text hover (28 April 2020) morphs menu labels through an SVG goo filter. It is adjacent to the lab’s Jelly and was not added. — [Codrops gooey text](https://tympanus.net/codrops/2020/04/28/morphing-gooey-text-hover-effect/)
- A calm 2D mouse-repel was not given a candidate. Edgeless does include an inverse-square push, but a free push overlaps the lab’s Scatter (“the cursor bats them away and they bounce home”), GSAP inertia (“throws pieces away… they slide and settle”), and Explode. A baseline-only slide of a few pixels would be new, and no source for that constrained version was found.

## What fails when the subject is a bitmap logo rather than live text?

### Takeaway

Anything that needs a glyph, a font axis, a counter, or a vector contour fails on a flattened logo. Channel offset, a cursor-shaped hole, and an alpha mask over a moving fill still work. Tracing the bitmap to get a path back is a different mark, not a recovery of the original one.

### Cited Findings

- Weight, width, slant, optical size, and casual axes are `font-variation-settings` on text. magnetType says the effect is invisible on a non-variable font, which includes a PNG. — [magnetType](https://github.com/Liiift-Studio/MagnetType); [Fancy Components](https://www.fancycomponents.dev/docs/components/text/variable-font-and-cursor)
- COLR palette swap applies to a color font (Honk, Nabla in the CSS-Tricks examples). A bitmap has no palette index. Recoloring the whole image is the lab’s Duotone. — [CSS-Tricks, `font-palette`](https://css-tricks.com/almanac/properties/f/font-palette/)
- Stroke draw-on needs a monoline path. Hoebregts: a normal filled typeface cannot do it, and a filled logo exported as shapes is the same problem. `getTotalLength()` is an SVG path method. — [Codrops, 31 Jan 2023](https://tympanus.net/codrops/2023/01/31/bringing-letters-to-life-coding-a-kinetic-svg-typography-animation/)
- Inner-stroke fill needs a path and a clip of that path. Kirk-Nielsen’s `stroke-width` tween has nothing to attach to on a PNG. — [chriskirknielsen.com](https://chriskirknielsen.com/blog/animate-an-svg-inner-stroke/)
- A stitch is a dashed path plus a mask path. Same failure. — [Motion Tricks](https://www.motiontricks.com/svg-dashed-line-animation/)
- Circular placement and tracking need per-letter advances. A bitmap wordmark has one box. `letter-spacing` does not apply to an image. — [CodeFronts](https://codefronts.com/motion/css-hover-effects/css-letter-spacing-expand-hover-effect/); [Codrops circular text](https://tympanus.net/codrops/2021/03/03/circular-svg-text-animation/)
- Split-flap per letter needs glyph boxes and clipped halves. One logo image can flap as a single tile only. — [vawe](https://vawe.dev/moves/flap-resolve)
- Counters exist as transparent holes only in an alpha-aware file. A JPEG, or a PNG of the logo on a solid rectangle, has no counter to fill. Even with alpha, the hole is a transparent region, not a separate path, so “fill the counter” means detecting enclosed holes. That detection was not sourced.
- Edgeless-style per-letter mass, spring, and collision need one body per letter. A bitmap is one body unless it is cut by hand. — [Edgeless Lab](https://edgelesslab.com/blog/kinetic-type-physics/)
- What still works on a bitmap: stacked channel copies with blend modes (Coltography does this with logo images); a radial mask or `destination-out` hole following the pointer (the x-ray construction, applied to an image); using the logo’s alpha as a mask over a scrolling fill, if the file is transparent. — [Coltography](https://coltography.ca/creating-a-dynamic-logo-with-css-and-additive-color-mixing/); [shadcn.io, Xray Text](https://www.shadcn.io/text/xray-text)

### Inferences

- Logos mode should prefer candidates 9/14 (chromatic stack), 13 (hole), and, only when the mark is actually SVG, 10, 11, and 12.
- Headline mode should prefer 1, 2, 3, 4, 5, 6, and 7. Candidate 8 is headline-only and easy to accidentally rebuild as Drop.
- If a client logo arrives as a PNG, do not trace it to unlock stroke draw. The trace changes joins, counters, and stroke contrast, so the hover would be happening to a different mark.

### Gaps

- No test in this pass loaded a real client logo from the lab into a browser, so the bitmap failures are from how the sourced techniques are built, not from a visual check against the lab’s logo set.
- Awwwards and Godly were not watchable as video in this pass. Marquee and “SVG mask hover” are confirmed as titles and credits, not as frame-by-frame descriptions.
