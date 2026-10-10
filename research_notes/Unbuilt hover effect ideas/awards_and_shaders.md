# Award-site and shader hover effects still missing from the lab

Scope: hover fidgets a logo or headline could still grow, drawn from Awwwards, Godly, CSSDA, FWA, Codrops, and public studio notes, 2022–2026 plus a few canonical effects those years kept reviving. Today is 10 October 2026. The lab already has Pixel burst, Jelly, Magnetic, Liquid ripple, Shatter, Glitch (RGB slice), Halftone, Scatter, Sand, Swirl, Lens magnifier, Wave, Pixelate, Highlighter, ASCII, 3D tilt, Dissolve, Black hole, Echo, Focus, Filings, Bulge, Pinch, Glow, Pluck, Confetti, Melt, Spotlight, Drop, Dock zoom, VHS, Duotone, and the GSAP set (elastic, explode, scramble, 3D flip, wiggle, inertia, swap, orbit, cascade, smear). None of those are recommended below, including under a new name.

Fifteen effects are kept. Each has a source URL. Feasibility is an engineering judgment against those sources, marked as inference, not a claim the source itself made.

## Which hover interactions keep winning awards in 2023–2026 and are still missing?

### Takeaway

The award loop in this window is still refraction glass, a cursor that melts or trails, and a reveal that slices or wipes an image. CSSDA and FWA did not yield a browsable hover-element catalog in this pass; the triple-award sites that did surface (Active Theory v6, LO2S) are WebGL studio pieces, not portable card fidgets. Of the prompt’s candidate list, the ones with a real 2023–2026 citation and no lab twin are liquid-glass refraction, a radial chromatic lens, gooey metaballs, image trail, blinds, mask wipe, page-peel/curl, stitch/outline trace, and (as a still-image cousin of awarded dither) ordered dither.

### Cited Findings

**Refraction / liquid glass is an awarded 2025 hover, and it is a GPU effect on the award sites.**

- Awwwards indexes “WebGL Refraction hover effect” from Dorian Lods Portfolio 2025, tagged webgl, glsl, and gpgpu. — [Awwwards](https://www.awwwards.com/inspiration/webgl-refraction-hover-effect-dorian-lods-portfolio-2025)
- Awwwards also indexes “Liquid Magic Interaction” from Hayden Bleasel’s Refraction, tagged liquid, interaction, magic. The element page does not name a year or a renderer. — [Awwwards](https://www.awwwards.com/inspiration/liquid-magic-interaction-refraction)
- Apple introduced Liquid Glass at WWDC in June 2025. A kube.io write-up rebuilds refraction with SVG displacement maps and a specular rim, and states that using an SVG filter as `backdrop-filter` works in Chrome only. — [kube.io](https://kube.io/blog/liquid-glass-css-svg)
- liquidGL (GitHub repo created 21 June 2025, author credit jrvanstone / NaughtyDuk) is a WebGPU library with WebGL fallback that refracts a live page snapshot, and ships chromatic aberration, fluid pointer interaction, frost, and specular highlights. — [GitHub](https://github.com/naughtyduk/liquidGL)

**Chromatic aberration shows up both as a glitch (already in the lab) and as prism dispersion on a lens (not in the lab).**

- liquidGL’s aberration option “disperses the red and blue channels either side of the refraction vector, blue displaced further than red,” and “concentrates at the bevelled edge and vanishes at the flat centre.” — [GitHub](https://github.com/naughtyduk/liquidGL)
- A 29 April 2026 write-up of a WebGL RGB-shift image card describes GSAP tweening a shader uniform so red and green sample offset UVs on hover, combined with a 3D tilt. — [freefrontend.com](https://freefrontend.com/code/webgl-rgb-shift-image-card-2026-04-29/)
- Awwwards indexes “Glitch Chromatic Aberration 404 with Digit Scramble” from Brilliant Digital. That title pairs aberration with glitch and digit scramble, which is the family the lab already calls Glitch (RGB slice). No year is on the fetched snippet. — [Awwwards](https://www.awwwards.com/inspiration/glitch-chromatic-aberration-404-with-digit-scramble-brilliant-digital-2)

**Gooey metaball cursors were a 2023 Codrops / studio pattern, implemented with SVG filters, not Three.js.**

- On 7 June 2023 Codrops published a gooey cursor: a grid of boxes revealed under the pointer, merged with `feGaussianBlur` plus an `feColorMatrix` alpha threshold, plus a CSS blend mode. Codrops credits the interaction to ETStudio5 on Lorenzo Dal Dasso’s site, and an edit credits Lama Lama as the earlier version. Lucas Bebber’s older “Creative Gooey Effects” is named as the filter lineage. Firefox is called out as needing a no-filter fallback. — [Codrops](https://tympanus.net/codrops/2023/06/07/gooey-cursor-effect/)
- A separate WebGL metaball playground by Jakub Antalík is documented at gooey.jakubantalik.com. No year is given. — [ShinUI](https://www.shinozaki.design/resource/gooey-jakub)

**Image trails are a revived Awwwards-style hero, and at least one current implementation is DOM animation rather than a shader.**

- Codrops, 21 October 2019 (canonical, outside the window, still the clearest primary tutorial): a Three.js hover plane follows the pointer, with RGB displacement, an image trail of several planes, and a stretch. GSAP smooths the motion. — [Codrops](https://tympanus.net/codrops/2019/10/21/how-to-create-motion-hover-effects-with-image-distortions-using-three-js/)
- GodUI’s Image Trail emits images along the pointer with the Web Animations API, spaced by a pixel threshold, then tilts, drifts, and fades. It disables the trail under `prefers-reduced-motion`. No year is stated. — [GodUI](https://godui.design/docs/lab/effects/image-trail)
- NedDev Lab describes the same pattern as a “classic awwwards hero” and shows a GSAP timeline (opacity, scale, rotation, then fade and drift) as one driver. No year is stated. — [NedDev](https://neddev.com/en/lab/hero/cursor-image-trail/)
- A breakdown of Active Theory names “cursor trail” as one of the site’s effects and says the site is “Built with WebGL on their internal framework, Hydra.” It does not date the trail or say the trail itself is a shader. — [whatthefrontend](https://www.whatthefrontend.com/sites/active-theory/)

**Sliced blinds and directional wipes are 2023 GSAP / CSS-mask hovers with named studio sources.**

- Codrops, 21 June 2023, recreates the sliced image hover from Quai Network: the image is cut into clip-path slices, a wrapper translates one way, slices translate the other, GSAP plays the reveal. Slice count and vertical vs horizontal orientation are settings. — [Codrops](https://tympanus.net/codrops/2023/06/21/coding-the-sliced-image-hover-effect-from-quai-network/)
- Artur Bień, 4 April 2023, documents a blinds mask (repeating linear gradients) and a wipe mask (a linear gradient whose position is a custom property). Support notes: `@property` was Chrome 85+ and Safari 16.4+ at that date; some composites needed a `-webkit-mask-composite` fallback. — [expensive.toys](https://www.expensive.toys/blog/fancy-css-reveal-effects)
- Codrops, 1 March 2023, “Double Image Hover Effects with Clip-Path Animations”: clip-path on hover, CSS filters during the animation, `step()` easing for a staggered look, GSAP among the tags. — [Codrops](https://tympanus.net/codrops/2023/03/01/double-image-hover-effects-with-clip-path-animations/)
- Codrops, 13 March 2024, “Grid Item Reveal Animation on Hover,” explicitly inspired by the Metalab site, GSAP-tagged. The fetched text does not specify clip-path versus another reveal. — [Codrops](https://tympanus.net/codrops/2024/03/13/grid-item-reveal-animation-on-hover/)

**Page peel / curl exists as both a WebGL component and a GSAP-only sticker flap.**

- Canvas UI’s Peel component peels a live page from an edge on cursor or hover. The docs page is a WebGL/GLSL component and offers a WebGPU/WGSL build. Options include side, mode (`cursor` or `hover`), reveal, zone, and curl. No year is stated. — [Canvas UI](https://canvasui.dev/docs/components/peel)
- GSAP Vault’s Sticker Peel “runs on GSAP core alone: no plugins, no canvas, no WebGL,” and describes a flap whose reflection is a matrix, with `transform-origin: 0 0`. No year is stated. — [GSAP Vault](https://gsapvault.com/effects/sticker-peel)

**Stitch / embroidery outline is documented as SVG dashoffset plus GSAP, on scroll rather than hover.**

- A “Scroll Thread Stitch Reveal” snippet draws a dashed SVG stroke with GSAP, parks a needle on `getPointAtLength`, and fades a filled shape in over the last portion of the timeline. No studio, award, or year is stated. — [webdevpuneet](https://webdevpuneet.com/ui-snippets/scroll-thread-stitch-reveal/)

**Dither, pixel-mosaic, and smoke are on Awwwards as shader interactions. Posterize, pencil, grain, emboss, and inner shadow did not appear as award hovers in this pass.**

- Awwwards indexes “Interactive dither effect” from Outsource Consultants, Inc, tagged dither, interaction, webgl, three.js, pixelation. No year. — [Awwwards](https://www.awwwards.com/inspiration/interactive-dither-effect-outsource-consultants-inc)
- Awwwards indexes “Interactive hero with dither plasma, and pixelated mouse flow distortion” from Codapress Publishing (Dave Holloway), tagged dither, plasma, mouse flow, fluid, pixel. No year. — [Awwwards](https://www.awwwards.com/inspiration/interactive-hero-with-dither-plasma-and-pixelated-mouse-flow-distortion-with-colour-change-on-press-codapress-publishing)
- Awwwards indexes “Pixel distortion image mouse interaction” from the same Codapress credit, tagged shaders, distortion, mouse flow, pixelation, canvas. No year. — [Awwwards](https://www.awwwards.com/inspiration/pixel-distortion-image-mouse-interaction-codapress-publishing)
- Awwwards indexes “Pixel-mosaic page transitions” from Catalin Vintila’s portfolio, tagged pixel, transition, dithering, motion, interaction. It is a page transition, not a hover. No year. — [Awwwards](https://www.awwwards.com/inspiration/pixel-mosaic-page-transitions-catalin-vintila-portfolio)
- Awwwards indexes “Fractal Hover Interaction” from Eva Sánchez Portfolio 2024. The fetched element page does not say what the fractal is built with. — [Awwwards](https://www.awwwards.com/inspiration/fractal-hover-interaction-eva-sanchez-portfolio-2024)
- Awwwards indexes “Cursor with Smoke Effect Distortion” from PANAMÆRA, credited to TOOSOON, tagged webgl, shaders, glsl, smoke, distortion. No year. — [Awwwards](https://www.awwwards.com/inspiration/cursor-with-smoke-effect-distortion)
- MakeMySketch, a canvas photo toy with no award claim and no date, describes pencil sketch as grayscale, invert, blur, and color-dodge, and cartoon/poster as Sobel edges plus posterize. — [MakeMySketch](https://makemysketch.com/)
- CHI 2023 paper filtered.ink (Jeff Huang and colleagues) treats `feTurbulence`, `feDisplacementMap`, `feConvolveMatrix`, and lighting primitives as the SVG toolkit for dynamic illustration. It is a drawing tool, not a hover award. — [CHI 2023 PDF](https://jeffhuang.com/papers/FilteredInk_CHI23.pdf)
- MDN documents `feTurbulence` as Perlin noise for textures such as clouds or marble, available across browsers since July 2015. — [MDN](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/feTurbulence)

**Studio awards in this window are real, and the public write-ups describe WebGL programs, not a card effect.**

- Richard Zhou’s case note on Active Theory v6 (Spring 2024; tools WebGL, GLSL, Houdini) lists Awwwards Site of the Day 6 February 2024, Awwwards Site of the Month February 2024, FWA of the Day 25 January 2024, FWA of the Month January 2024, CSS Design Awards Website of the Day 13 February 2024, and CSS Design Awards Website of the Year 2024 nominee, runner-up. The note does not describe a hover. — [richardczhou.com](https://www.richardczhou.com/posts/atv6)
- RDK’s case on LO2S by SALT AND Pepper says the 2025 portfolio used an endless 3D gallery and custom shaders for text and logo animation, and lists Awwwards, CSSDA, and FWA day awards. The same page first says “Awwwards 2025 — Site of the day” and later “Honorable Mention Site of the Day.” Those two Awwwards wordings conflict; CSSDA Website of the Day and FWA of the Day are stated in both places. — [RDK](https://rdk.digital/case/lo2s)
- Immersive Garden’s Awwwards case study says animation used GSAP and scroll used Lenis. A Communication Arts pick of the same site adds WebGL, three.js, Vue/Nuxt, and 3D tools, and describes 3D Roman numerals. Neither page describes a new image or type hover. — [Awwwards case study](https://www.awwwards.com/case-study-immersive-gardens-new-website.html); [Communication Arts](https://www.commarts.com/webpicks/immersive-garden)
- A design teardown of Immersive Garden describes a two-layer custom cursor (one follower snaps, one lerps) and a 120-dot scroll cursor. No date. — [modern-design.md](https://github.com/Shuvam-Banerji-Seal/modern-design.md/blob/main/websites/immersive-g/design.md)
- Godly’s custom-cursor filter returns a list of sites (Andreas Antonsson, José Meza, Ruben Wyttenbach Photography, Mike Matas, Antonio Uve, Gareth Hughes, BelArosa Chalet, La Puce À L'oreille). The result does not describe any site’s hover. — [Godly](https://godly.website/?animation=%5B%22custom-cursor%22%5D)
- Awwwards indexes “Image effect reactive cursor” from CUSP, tagged reactive cursor, image effect, filter, webgl. No year and no further mechanism. — [Awwwards](https://www.awwwards.com/inspiration/image-effect-reactive-cursor-cusp)

### Inferences

Kept, because a source names the interaction, the lab does not already ship it, and a logo or headline can host it:

1. Liquid-glass refraction on the card’s own bitmap (not a live-page lens).
2. Chromatic aberration as a radial lens, not an RGB slice.
3. Gooey metaball cursor.
4. Image trail.
5. Blinds / sliced reveal.
6. Directional mask wipe.
7. Page peel / curl as a flap.
8. Stitch and outline trace, one effect (embroidery fill is the last beat of the same timeline).
9. Ordered dither inside the pointer radius.
10. Posterize inside the pointer radius. Award evidence is missing; the canvas technique is sourced.
11. Pencil sketch inside the pointer radius. Same evidence caveat.
12. Emboss inside the pointer radius. Same evidence caveat, via the convolution primitive.
13. Grain reveal inside the pointer radius. Same evidence caveat, via turbulence noise.
14. Mosaic tile flip. The award citation is a page transition, so this is an adaptation.
15. Smoke as a particle fidget on the pointer. The awarded PANAMÆRA piece is shader distortion; the particle version is a different, weaker effect that still reads as smoke on a wordmark.

Not kept, with the reason:

- Bulge, as shipped by Robin Payot’s 28 June 2023 Codrops/OGL tutorial. The lab already has Bulge. — [Codrops](https://tympanus.net/codrops/2023/06/28/creating-a-bulge-distortion-effect-with-webgl/)
- Brilliant Digital’s glitch chromatic 404. It is the lab’s RGB-slice glitch plus scramble.
- The 3D tilt half of the April 2026 RGB-shift card. The lab already has 3D tilt.
- Jakub Antalík’s WebGL metaball fluid. The SVG gooey cursor covers the fidget without a new renderer.
- PANAMÆRA / TOOSOON smoke distortion as a warp of the image. That one is GLSL. Only the particle cousin is kept.
- Codapress dither plasma and Outsource Consultants’ Three.js dither, as fluid simulations. Only a still ordered dither is kept.
- Canvas UI’s cylindrical peel. The docs are WebGL/WebGPU. Only the GSAP flap is kept.
- liquidGL and Dorian Lods’ gpgpu refraction, as engines. They refract a live scene and, in Lods’ case, a GPU fluid. A card-local displacement is the kept slice.
- LO2S text and logo shaders (SALT AND Pepper, 2025). No public breakdown of a 2D approximation was found.
- Active Theory v6’s environments (2024). WebGL/GLSL/Houdini, not a card hover.
- Immersive Garden’s 3D numerals. three.js.
- Immersive Garden’s lerping cursor, and any “sticky cursor” pattern. The lab already has Magnetic and inertia.
- Evervault’s radial gradient mask, Codrops 17 May 2023. The lab already has Spotlight. — [Codrops](https://tympanus.net/codrops/2023/05/17/recreating-the-gradient-mask-hover-effect-from-evervault/)
- sink.design’s mouse-following text rows, Codrops 29 May 2024. Reads as the lab’s Wave. — [Codrops](https://tympanus.net/codrops/2024/05/29/hover-motion-intro-animation/)
- Alena Orlova’s skewed grid hover, Codrops 13 September 2023. Reads as the lab’s Smear. — [Codrops](https://tympanus.net/codrops/2023/09/13/grid-item-hover-effect/)
- Goop, as a separate idea. It is the gooey cursor again.
- Cloth. No 2022–2026 award hover was found, and a verlet sheet is a new simulation family.
- Inner shadow. No award hover was found. An inset CSS shadow is not a fidget.
- Slit scan. The only retrieved description is Synthetik’s desktop temporal video process, not a web hover. — [Synthetik](https://synthetik.com/adjusting-slit-scan-effects-scan-direction/)
- liquid-distort’s swirl, ripple, and wave modes. The lab already has those. Its refract mode is relevant only as evidence for effect 1. — [npm](https://www.npmjs.com/package/liquid-distort)

### Gaps

- No Shadertoy hover page was retrieved. Nothing here is credited to a Shadertoy author.
- No Resn case study with a named hover technique was retrieved.
- Godly’s cursor index and the CUSP Awwwards element were not opened far enough to name the actual interaction.
- FWA and CSSDA do not appear, in this pass, as element galleries comparable to Awwwards Elements. Award evidence for those two is studio self-reporting (Active Theory v6, LO2S).
- Eva Sánchez’s 2024 fractal hover has no published mechanism in the snippet, so it is not mapped onto mosaic, dither, or anything else.
- Posterize, pencil, grain, and emboss have implementation sources and no award-site hover page. They are kept as canvas fidgets with that limit stated.
- Hayden Bleasel’s “Liquid Magic” element has no year and no stack on the fetched page.
- Publication years are missing for GodUI, Canvas UI Peel, GSAP Vault Sticker Peel, MakeMySketch, PANAMÆRA smoke, both dither elements, Catalin Vintila’s mosaic, and the stitch snippet.

## For each, what is the usual implementation, and can this lab do it in Canvas 2D or GSAP?

### Takeaway

Eight of the fifteen can be the real effect, not a compromise: gooey (SVG filter), image trail (GSAP or WAAPI), blinds, mask wipe, stitch trace, posterize, ordered dither, and grain. Liquid glass, the chromatic lens, peel, emboss, sketch, mosaic, and smoke survive as hover fidgets with a stated loss. Live-scene refraction, smoke that warps the picture, plasma dither, and a cylindrical peel do not survive without a new WebGL family.

### Cited Findings

- liquid-distort builds a cursor distortion by painting a displacement map on a small canvas and feeding it to SVG `feDisplacementMap`. The package page says “No WebGL,” and lists modes `refract`, `attract`, `swirl`, `ripple`, and `wave`. — [npm](https://www.npmjs.com/package/liquid-distort)
- kube.io encodes refraction as an 8-bit red/green displacement image. Neutral is 128, so each axis can shift about −128 to 127 pixels, and `feDisplacementMap`’s `scale` multiplies that. The author animates `scale` rather than rebuilding the map. — [kube.io](https://kube.io/blog/liquid-glass-css-svg)
- liquidGL states that WebGL cannot read live screen pixels, so the library snapshots the page offscreen to refract video and text. A CSS `backdrop-filter` blur is the last fallback in its engine chain, after WebGPU, WebGL2, and WebGL1. — [GitHub](https://github.com/naughtyduk/liquidGL)
- Codrops’ gooey filter is `feGaussianBlur` (`stdDeviation="3.2"`) into an `feColorMatrix` whose alpha row is `0 0 0 20 -7`, then `feComposite` atop the sharp source. The article’s tags include GSAP and “Motion Trail.” — [Codrops](https://tympanus.net/codrops/2023/06/07/gooey-cursor-effect/)
- GodUI’s Liquid Metaballs use an SVG goo filter, one extra blob on the cursor, and a `gooeyness` prop described as blur `stdDeviation` (default 16). — [GodUI](https://godui.design/docs/lab/backgrounds/liquid-metaballs)
- GodUI’s Image Trail keeps a recycled pool of elements and spawns with the Web Animations API once the pointer has moved `threshold` pixels. Defaults: threshold 64, duration 750 ms, max 12, size 180. — [GodUI](https://godui.design/docs/lab/effects/image-trail)
- The Quai Network recreation sets each slice’s `clip-path` to a percentage polygon and animates with GSAP. Orientation picks columns or rows. — [Codrops](https://tympanus.net/codrops/2023/06/21/coding-the-sliced-image-hover-effect-from-quai-network/)
- Bień’s wipe is a `mask-image` linear gradient whose stop is the custom property `--wipe-position`, transitioned over 600 ms. Blinds use a repeating gradient in the same role. — [expensive.toys](https://www.expensive.toys/blog/fancy-css-reveal-effects)
- Canvas UI Peel is documented as a WebGL component (WebGPU optional), driven by pointer position in a zone along one edge. — [Canvas UI](https://canvasui.dev/docs/components/peel)
- GSAP Vault Sticker Peel states it uses GSAP core only, with a flap element, a reflection matrix, and CSS drop-shadow for the underside silhouette. — [GSAP Vault](https://gsapvault.com/effects/sticker-peel)
- The stitch snippet is SVG `stroke-dasharray` plus a GSAP timeline, needle pose from `getPointAtLength`, fill opacity at the end. — [webdevpuneet](https://webdevpuneet.com/ui-snippets/scroll-thread-stitch-reveal/)
- MakeMySketch attributes pencil rendering to canvas grayscale, invert, blur, and color-dodge, and poster/cartoon rendering to Sobel plus posterize, all in HTML canvas. — [MakeMySketch](https://makemysketch.com/)
- filtered.ink (CHI 2023) lists `feConvolveMatrix` among the primitives used for pattern perturbation and lighting. — [CHI 2023 PDF](https://jeffhuang.com/papers/FilteredInk_CHI23.pdf)
- PANAMÆRA’s smoke cursor and both Awwwards dither pieces are tagged as WebGL/shaders or Three.js, as cited in the previous section.

### Inferences

Feasibility for this lab. “Radius” and “strength” stay the shared pair; the third knob is in the next section.

1. **Liquid-glass refraction.** Usual stack is a shader (Dorian Lods; liquidGL) or an SVG displacement map (kube.io; liquid-distort’s `refract` mode). Credible on a card: render the card to a bitmap, build a small displacement field in Canvas 2D the way liquid-distort does, and resample pixels along that field, stronger at a bezel and near zero at the center. Quality lost: Snell’s law on a real bezel profile, specular rim, frost, stacked lenses, and refraction of whatever is behind the card. Those last items are why liquidGL exists. Do not take this on as a live-page lens.
2. **Chromatic lens.** Usual stack is the same shader, with red and blue offset along the refraction vector (liquidGL; the April 2026 RGB-shift card). Credible in Canvas 2D: three samples of the card bitmap, red and blue shifted in opposite directions along the vector from the pointer, offset falling to zero at the center of the radius. Quality lost: dispersion that follows a bevel normal rather than a simple radial vector, and blue-versus-red wavelength weighting. This is not the lab’s horizontal RGB slice.
3. **Gooey metaball cursor.** Usual stack is the SVG filter above, not WebGL. The lab can do the real effect with SVG plus GSAP (or plain element positions) beside the card. A Canvas 2D blur-and-threshold is a fallback if SVG filters are refused, and it loses the blend-mode color variants Codrops used. Firefox’s poor filter behavior is a cited constraint, so a no-filter fallback has to exist.
4. **Image trail.** Usual awarded version in the 2019 tutorial is Three.js. The current DOM versions (GodUI, NedDev) are the effect itself: recycled elements, spawn by distance, fade and drift. GSAP can own the whole thing. Nothing important is lost relative to those DOM versions. The shader trail’s RGB smear and mesh bend are a different, rejected effect.
5. **Blinds.** Usual stack is GSAP and `clip-path` (Quai Network, 2023) or a repeating CSS mask (Bień, 2023). Full quality in GSAP. Best on a headline or a card image, not on a tiny logo.
6. **Mask wipe.** Usual stack is CSS mask or clip-path, with GSAP or a custom-property transition (Bień; Codrops double-image hovers, March 2023). Full quality in GSAP. Distinct from Spotlight, which is a radial hole, and from Dissolve, which is a fade.
7. **Page peel / curl.** The awarded-looking live peel (Canvas UI) is WebGL and should be rejected as a new family. The GSAP flap (GSAP Vault) is the credible version: a corner element scales or rotates open, a shadow sits on the fold, the underside is a mirrored copy. Quality lost: a cylindrical curl, shading that tracks the fold, and a true backside reflection. Good on a card; awkward on a one-line headline.
8. **Stitch / outline trace.** Usual stack is SVG stroke dashoffset and GSAP. On a logo path this is the real effect, including a short embroidery fill at the end of the dash. Canvas 2D can stroke the same dashes if the mark is not already SVG. Quality lost in canvas: the needle’s tangent is fussier, and a dashed stroke on rasterized type looks mechanical.
9. **Ordered dither.** Awarded versions are Three.js or a plasma mouse-flow shader. Those fluid versions are rejected. A Bayer (or similar) threshold of the card’s pixels inside the radius is a faithful still dither in Canvas 2D, and it is not Halftone (dots), Pixelate (blocks), or ASCII. Quality lost: animated plasma and the way Codapress couples dither to a fluid sim.
10. **Posterize.** No award implementation was found. MakeMySketch does it on canvas by quantizing color. That is the whole effect, so Canvas 2D loses nothing important. Sobel edges on top would turn it into their cartoon mode; keep that optional so it does not collapse into the sketch.
11. **Pencil sketch.** No award implementation was found. MakeMySketch’s canvas recipe (grayscale, invert, blur, color-dodge) is the usual 2D method. Quality lost versus a shader sketch: animated hatching that follows curvature, and a paper-tooth displacement. Fine as a hover on a wordmark.
12. **Emboss.** No award hover was found. `feConvolveMatrix` is the SVG version; the same 3×3 kernel on canvas pixels is the Canvas 2D version. Quality lost: `feSpecularLighting` / `feDiffuseLighting`, which filtered.ink treats as separate primitives. Enough for a logo fidget.
13. **Grain reveal.** No award hover was found. `feTurbulence` is the usual noise source; Canvas 2D can fill a radial mask with film grain and reveal the card through it. Full quality for a grain wipe. It is not the lab’s Dissolve (no noise structure) and not VHS (no scan lines or chroma bleed).
14. **Mosaic tile flip.** Catalin Vintila’s citation is a pixel-mosaic page transition tagged dithering, so a hover of tumbling tiles is an adaptation, not a reproduction. GSAP can flip a grid of tiles in place (each tile a background-position window). Quality lost versus a shader mosaic: per-pixel resampling and the dithering tag on that transition. Distinct from Pixelate if the tiles physically turn rather than block-averaging, and from Shatter if they stay in the grid.
15. **Smoke.** The Awwwards element is a GLSL distortion and is rejected as a warp. A Canvas 2D or GSAP particle sprite trail (short life, rising, fading) is a credible fidget on a headline and loses the entire distortion: no density field, no light scatter, no bending of the letters. Ship it only as particles, named as such.

### Gaps

- CUSP’s “image effect reactive cursor” is tagged WebGL and was not described well enough to judge a 2D port.
- No source in this pass shows a production Canvas 2D port of liquid glass, only the SVG-displacement route (kube.io, liquid-distort) and the WebGPU/WebGL route (liquidGL).
- The stitch source is scroll-driven. Hover behavior is an adaptation.
- Cloth and slit scan have no web-hover implementation page here, so they were not given a 2D port.

## What extra knob would make it tunable the way the lab tunes radius and strength? Name the studio or demo and the year.

### Takeaway

Where a 2023–2026 source already exposes a third control, use that control’s real name. Radius and strength stay the lab’s pair; the extra knob is the one that changes the character of the fidget rather than its size or intensity. Years are stated only when the source states them.

### Cited Findings

- liquidGL (repo created 21 June 2025): `refraction` default 0.01, range 0–1; `aberration` range 0–1, default 0; `bevelDepth` default 0.08; `bevelWidth` default 0.15; `frost` in pixels; fluid mode adds `interactionStrength`, `interactionRadius`, and `interactionViscosity`. — [GitHub](https://github.com/naughtyduk/liquidGL); demo copy of the refraction range — [liquidgl.naughtyduk.com](https://liquidgl.naughtyduk.com/demos/demos/fluid-interaction.html)
- kube.io (describing Apple’s June 2025 Liquid Glass): surface profile is a named choice (convex circle, convex squircle, concave, lip), plus bezel width, glass thickness, and displacement `scale`. — [kube.io](https://kube.io/blog/liquid-glass-css-svg)
- liquid-distort: `radius`, `strength`, `frequency`, `falloff`, and `mode`. No year on the fetched page. — [npm](https://www.npmjs.com/package/liquid-distort)
- Codrops gooey cursor, 7 June 2023: blur `stdDeviation` 3.2 and color-matrix alpha row `20 -7`. GodUI names the blur `gooeyness` (default 16) and also exposes `blobCount`. — [Codrops](https://tympanus.net/codrops/2023/06/07/gooey-cursor-effect/); [GodUI](https://godui.design/docs/lab/backgrounds/liquid-metaballs)
- GodUI Image Trail: `threshold` (spacing), `duration`, `max`, `size`. NedDev’s GSAP version uses a 48 px distance gate and a random rotation. No years. — [GodUI](https://godui.design/docs/lab/effects/image-trail); [NedDev](https://neddev.com/en/lab/hero/cursor-image-trail/)
- Quai Network via Codrops, 21 June 2023: `slicesTotal` and `orientation`. — [Codrops](https://tympanus.net/codrops/2023/06/21/coding-the-sliced-image-hover-effect-from-quai-network/)
- Bień, 4 April 2023: `--gradient-length` (wipe softness, example 20%) and the blinds’ repeating-gradient period. — [expensive.toys](https://www.expensive.toys/blog/fancy-css-reveal-effects)
- Canvas UI Peel: `curl` in CSS pixels (“smaller curl, sharper fold”), plus `reveal` and `zone`. GSAP Vault does not publish a matching numeric knob on the fetched page. No years. — [Canvas UI](https://canvasui.dev/docs/components/peel); [GSAP Vault](https://gsapvault.com/effects/sticker-peel)
- Stitch snippet: dash pattern `6 6` and a stitch phase that occupies the first 90% of the timeline before the fill. No year. — [webdevpuneet](https://webdevpuneet.com/ui-snippets/scroll-thread-stitch-reveal/)
- MakeMySketch: blur radius controls pencil softness; the page does not name a posterize level count. No year. — [MakeMySketch](https://makemysketch.com/)
- Codapress (Dave Holloway) and Outsource Consultants publish no public knob list on the Awwwards element pages. PANAMÆRA’s smoke element page likewise has tags only.

### Inferences

Proposed third knob, beside the lab’s radius and strength. The knob is taken from the source when the source has one, and invented only where the citation has no third control.

| Kept effect | Demo, studio, year | Extra knob | Why this one |
| --- | --- | --- | --- |
| Liquid-glass refraction | Dorian Lods, Awwwards, 2025; NaughtyDuk liquidGL, repo 21 June 2025; kube.io on Apple WWDC June 2025 | Bezel width (`bevelWidth` in liquidGL, default 0.15) | Strength is refraction. Bezel width decides whether the bend is a rim or the whole card. |
| Chromatic lens | liquidGL aberration, 2025; freefrontend RGB-shift card, 29 April 2026 | Dispersion (`aberration`, 0–1) | Independent of how hard the glass bends. Zero is a clear lens; high is a prism at the rim only. |
| Gooey metaball cursor | Codrops / ETStudio5 / Lama Lama, 7 June 2023 | Threshold (the `−7` in the color matrix, or GodUI `gooeyness`) | Strength can move blobs. Threshold is what makes them fuse. |
| Image trail | Codrops trail, 21 Oct 2019; GodUI; NedDev “awwwards hero”; Active Theory names a cursor trail, undated | Spawn gap (`threshold`, GodUI default 64 px) | Strength can scale the images. Gap is the difference between a smear and a procession. |
| Blinds | Quai Network via Codrops, 21 June 2023 | Slat count (`slicesTotal`) | The reveal reads as blinds only past a handful of slats, and as a single wipe at 1. |
| Mask wipe | Codrops clip-path hovers, 1 March 2023; Bień, 4 April 2023 | Softness (`--gradient-length`) | Angle can be a direction control. Softness is the difference between a hard cut and a fogged edge. |
| Page peel / curl | Canvas UI Peel (WebGL, undated) for the knob; GSAP Vault flap (undated) for the build | Curl radius | A tight curl looks like a sticker corner; a large one looks like a turned page. |
| Stitch / outline trace | SVG/GSAP stitch snippet, undated; no award studio found | Stitch length (dash on/off) | Short dashes read as embroidery; a solid dash reads as a pen trace. |
| Ordered dither | Outsource Consultants (Three.js, undated); Codapress / Dave Holloway plasma (undated) | Matrix size (2, 4, or 8) | Not in the source pages. It is the control that separates coarse newsprint from fine stipple, which Halftone’s dot size does not cover. |
| Posterize | MakeMySketch canvas, undated; no award | Level count | Not named in the source. Two levels is a photocopy; eight is a faded print. |
| Pencil sketch | MakeMySketch, undated; no award | Hatch softness (their blur radius) | Strength can darken the graphite. Softness is how much it looks drawn versus edged. |
| Emboss | filtered.ink convolution primitive, CHI 2023; no award hover | Light angle | Strength is the kernel weight. Angle is what makes the mark look struck from the upper left versus debossed. |
| Grain reveal | `feTurbulence`, MDN; no award hover | Grain scale (`baseFrequency`) | Strength is opacity of the noise. Frequency is coarse film versus fine dust. |
| Mosaic tile flip | Catalin Vintila pixel-mosaic transition, undated, adapted | Tile count | Same role as slat count. Too few and it is a flip; too many and it collapses toward Pixelate. |
| Smoke particles | PANAMÆRA / TOOSOON, Awwwards, undated, as the rejected shader; particles are the port | Dissipation (particle life) | Not published on the element page. Life is the difference between a puff on the letter and a fog that fills the card. |

### Gaps

- No source gives a public knob for PANAMÆRA smoke, Codapress dither, or Outsource Consultants dither. The matrix-size and dissipation knobs above are proposals.
- GSAP Vault does not publish a curl-radius number; that knob is taken from Canvas UI’s WebGL component and applied to the GSAP flap.
- Studio attribution is thin for stitch, posterize, sketch, emboss, and grain. They should not be described as award winners in the final report.
