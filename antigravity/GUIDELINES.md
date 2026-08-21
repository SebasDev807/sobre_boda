# Project Guidelines — Interactive Envelope

## 1. Core Stack

- Use Astro as the primary framework and application architecture.
- Use TypeScript throughout the project.
- Use Vanilla CSS for custom styling, layout, transitions and animations.
- React is allowed and should be used when a component benefits from client-side state, complex interactivity or reusable interactive behavior.
- Prefer Astro components for static/presentational content.
- Prefer React components for genuinely interactive UI.
- Do NOT use Tailwind CSS unless explicitly requested later.
- GSAP is allowed when CSS animations are insufficient for complex motion or timeline-based animations.
- Prefer native CSS animations and transitions before introducing GSAP.
- Do not introduce additional libraries without a clear technical reason.

## 2. Astro + React Architecture

Astro should remain the primary framework.

Use the following decision rule:

### Use Astro when:
- The component is mostly static.
- The component does not require client-side state.
- The component is primarily structural or visual.
- SEO and minimal JavaScript are priorities.

### Use React when:
- The component requires interactive state.
- The component has complex event handling.
- Multiple UI elements need synchronized state.
- A reusable interactive component would be significantly easier to maintain with React.
- Client-side interaction would otherwise require unnecessarily complicated vanilla JavaScript.

Do not convert the entire application to React unnecessarily.

Use Astro's React integration and hydration directives appropriately.

Prefer the smallest hydration scope possible.

For example:

- `Envelope.astro` → static envelope structure.
- `Hummingbird.astro` → SVG/visual structure.
- `Letter.astro` → static letter content.
- A complex interactive controller → React component if necessary.

Avoid hydrating components that do not require client-side JavaScript.

## 3. Design Goal

Create an elegant interactive webpage centered around a realistic paper envelope.

The experience should feel intimate, delicate and cinematic rather than like a generic landing page.

The envelope is the primary visual element of the experience.

The page should feel like opening a physical letter rather than interacting with a conventional website.

## 4. Envelope

The envelope should be constructed using HTML/CSS/SVG rather than a flat image.

It should visually resemble a physical paper envelope with:

- Front body
- Top flap
- Side folds
- Bottom fold
- Letter inside
- Subtle paper texture
- Soft shadows
- Realistic depth

The envelope should initially appear closed.

When opened:

1. The top flap rotates naturally around its upper edge.
2. The internal letter becomes visible.
3. The letter slides upward from inside the envelope.
4. The envelope maintains realistic depth.
5. Animations use smooth easing.
6. The interaction should feel physical rather than mechanical.

Use CSS 3D transforms where appropriate.

Important properties:

- perspective
- transform-origin
- rotateX
- rotateY
- translateY
- z-index
- backface-visibility

## 5. Envelope State

The envelope must have a clearly defined state:

- closed
- opening
- open

Prevent repeated clicks from corrupting the animation state.

If React is used to control the envelope, keep the state management simple.

Do not introduce a state-management library for a single interaction.

Prefer:

- React state
- CSS classes
- data attributes
- CSS custom properties

over unnecessary abstractions.

## 6. Hummingbird

Include a hummingbird flying around the envelope.

Prefer SVG for the hummingbird so it remains sharp at every resolution.

The hummingbird should:

- Move along a curved trajectory.
- Have subtle vertical movement.
- Slightly rotate according to its movement direction.
- Animate its wings independently.
- Feel organic rather than like an object moving linearly.
- Avoid excessive movement that distracts from the envelope.

Suggested sequence:

1. Hummingbird enters the scene.
2. It approaches the envelope.
3. It briefly hovers nearby.
4. User opens the envelope.
5. The hummingbird reacts to the opening.
6. It eventually flies away.

The hummingbird should feel like part of the scene, not a decorative GIF.

## 7. Animation Principles

Animations must prioritize:

- Smoothness
- Natural movement
- Physical plausibility
- Subtlety
- Consistent timing

Avoid:

- Excessive bouncing
- Generic fade-ins everywhere
- Extremely fast transitions
- Linear movement where natural motion would be better
- Excessive particle effects
- Gratuitous animations

Use appropriate easing for each physical action.

Examples:

- Envelope opening → smooth ease-out
- Letter movement → soft ease-out
- Hummingbird flight → organic/custom easing
- Wing movement → fast repeating animation

Use CSS transforms and opacity whenever possible.

Use GSAP only when a complex timeline or motion path genuinely benefits from it.

## 8. Visual Style

The visual language should feel:

- Elegant
- Romantic
- Warm
- Minimal
- Handcrafted
- Slightly magical

Avoid:

- Generic SaaS aesthetics
- Dashboard aesthetics
- Excessive gradients
- Excessive glassmorphism
- Neon colors
- Overly saturated UI
- Huge unnecessary typography
- Excessive decorative elements

The envelope and hummingbird should remain the visual focus.

## 9. Interaction

The experience must support:

- Mouse
- Touch
- Keyboard

Do not rely exclusively on hover.

The envelope should be accessible through keyboard interaction.

Use semantic interactive elements where appropriate.

Respect reduced-motion preferences using:

`prefers-reduced-motion`

Users who prefer reduced motion should receive a simplified version of the animation rather than having the experience become unusable.

## 10. Responsive Design

The experience must work on:

- Desktop
- Tablet
- Mobile

The envelope should scale proportionally.

The hummingbird trajectory should adapt to the viewport.

Do not simply shrink the desktop layout on mobile.

Recalculate positioning and animation distances where necessary.

Pay particular attention to:

- Small phone screens
- Portrait orientation
- Touch interaction
- Letter readability
- Animation clipping

## 11. Performance

Prefer GPU-friendly properties:

- transform
- opacity

Avoid unnecessarily animating:

- width
- height
- top
- left

when transforms can accomplish the same effect.

Avoid unnecessary JavaScript animation loops.

Use `requestAnimationFrame` only when genuinely necessary.

Keep React hydration limited to components that actually need it.

Optimize SVG assets.

Do not add large dependencies without justification.

## 12. Code Organization

Keep components small and understandable.

Suggested structure:

src/
├── components/
│   ├── Envelope.astro
│   ├── Hummingbird.astro
│   ├── Letter.astro
│   └── InteractiveEnvelope.tsx
├── layouts/
├── pages/
│   └── index.astro
├── styles/
│   ├── global.css
│   └── envelope.css
├── scripts/
└── assets/

Do not put the entire project into one file.

Keep animation styles organized.

Keep React logic separate from static Astro markup when practical.

Avoid unnecessary component fragmentation.

## 13. Styling Rules

Use Vanilla CSS as the primary styling system.

Prefer:

- CSS custom properties
- CSS nesting where appropriate
- semantic class names
- reusable animation definitions
- CSS keyframes
- transforms
- transitions

Avoid huge inline style attributes.

Avoid duplicating the same CSS values unnecessarily.

Use CSS variables for important design values such as:

- envelope dimensions
- animation durations
- easing functions
- colors
- shadows
- perspective

## 14. Development Process

Build the project incrementally.

Do NOT attempt to implement the entire experience in one step.

Recommended order:

1. Create the Astro project structure.
2. Build the static envelope.
3. Refine its proportions and visual appearance.
4. Implement the opening animation.
5. Implement the letter animation.
6. Add the hummingbird.
7. Animate the hummingbird flight.
8. Synchronize the envelope, letter and hummingbird animations.
9. Add interactive state where necessary.
10. Add responsive behavior.
11. Add accessibility and reduced-motion support.
12. Polish visual details.
13. Optimize performance.

After each major stage, verify that the existing functionality still works before continuing.

## 15. Agent Behavior

Before implementing a feature:

- Inspect the existing project structure.
- Reuse existing components and styles when appropriate.
- Do not rewrite working code unnecessarily.
- Do not introduce a new framework or dependency without justification.
- Do not replace custom animations with generic libraries or premade components unless explicitly requested.
- Preserve the established visual language.
- Prefer simple solutions over unnecessary abstractions.

When modifying an existing component, make the smallest reasonable change.

Do not refactor unrelated parts of the project.

## 16. Important Restrictions

Do NOT:

- Replace the envelope with a static image.
- Replace the hummingbird with a GIF unless explicitly requested.
- Replace the custom animation with a video.
- Use Tailwind unless explicitly requested.
- Convert the entire Astro project into React.
- Add unnecessary state-management libraries.
- Add unnecessary animation libraries.
- Generate a generic landing page around the concept.
- Add decorative UI elements that distract from the central experience.

The core experience must remain:

A beautiful interactive paper envelope that opens and reveals a letter, accompanied by a naturally flying hummingbird.

## 17. Quality Standard

The final result should feel like a carefully crafted interactive scene rather than a collection of web effects.

Every animation must have a purpose.

Every interactive element should feel intentional.

Prioritize:

1. Visual quality
2. Natural motion
3. User experience
4. Accessibility
5. Performance
6. Maintainable code

The goal is not to demonstrate how many technologies can be used.

The goal is to create a polished experience using the simplest technology appropriate for each part of the project.