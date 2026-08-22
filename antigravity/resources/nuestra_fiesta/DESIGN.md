---
name: Ethereal Earth
colors:
  surface: '#fff9ec'
  surface-dim: '#e0dac7'
  surface-bright: '#fff9ec'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#faf3e0'
  surface-container: '#f4eedb'
  surface-container-high: '#efe8d5'
  surface-container-highest: '#e9e2d0'
  on-surface: '#1e1c10'
  on-surface-variant: '#54433e'
  inverse-surface: '#333024'
  inverse-on-surface: '#f7f0dd'
  outline: '#86736d'
  outline-variant: '#d9c2ba'
  surface-tint: '#904b33'
  primary: '#88452d'
  on-primary: '#ffffff'
  primary-container: '#a65d43'
  on-primary-container: '#fff4f0'
  inverse-primary: '#ffb59c'
  secondary: '#725a41'
  on-secondary: '#ffffff'
  secondary-container: '#fdddbd'
  on-secondary-container: '#786047'
  tertiary: '#6e5247'
  on-tertiary: '#ffffff'
  tertiary-container: '#886a5e'
  on-tertiary-container: '#fff4f0'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#ffdbcf'
  primary-fixed-dim: '#ffb59c'
  on-primary-fixed: '#390c00'
  on-primary-fixed-variant: '#73351e'
  secondary-fixed: '#fdddbd'
  secondary-fixed-dim: '#e0c1a3'
  on-secondary-fixed: '#281805'
  on-secondary-fixed-variant: '#58432c'
  tertiary-fixed: '#ffdbcd'
  tertiary-fixed-dim: '#e3bfb0'
  on-tertiary-fixed: '#2a170e'
  on-tertiary-fixed-variant: '#5b4136'
  background: '#fff9ec'
  on-background: '#1e1c10'
  surface-variant: '#e9e2d0'
typography:
  display-lg:
    fontFamily: Playfair Display
    fontSize: 48px
    fontWeight: '600'
    lineHeight: 56px
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Playfair Display
    fontSize: 36px
    fontWeight: '600'
    lineHeight: 44px
  headline-md:
    fontFamily: Playfair Display
    fontSize: 24px
    fontWeight: '400'
    lineHeight: 32px
    letterSpacing: 0.05em
  body-md:
    fontFamily: Libre Franklin
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  label-sm:
    fontFamily: Libre Franklin
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.1em
  script-accent:
    fontFamily: Playfair Display
    fontSize: 64px
    fontWeight: '400'
    lineHeight: 64px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  container-margin: 24px
  gutter: 16px
  section-gap: 80px
  arch-top-padding: 120px
---

## Brand & Style

This design system is built for high-end digital wedding invitations and celebratory experiences. The brand personality is **romantic, timeless, and organic**, rooted in a sophisticated interpretation of Mediterranean and earthy aesthetics. It aims to evoke a sense of warmth, intimacy, and refined celebration.

The visual style blends **Minimalism** with **Tactile/Skeuomorphic** influences. It relies on generous white space (or "beige space"), high-quality serif typography, and organic architectural shapes—specifically the arch—to create depth without digital clutter. The mood is intentionally soft, avoiding harsh edges or bright synthetic colors in favor of a natural, sun-drenched palette.

## Colors

The palette is derived from natural earth pigments. 

- **Primary (Terracotta):** Used for primary actions, accents, and key decorative elements. It provides the "heart" of the warmth.
- **Secondary (Soft Sand):** Used for secondary surfaces, subtle buttons, and layered background elements.
- **Tertiary (Chocolate Brown):** Reserved for primary text and high-contrast borders to ensure legibility while maintaining a softer feel than pure black.
- **Neutral (Alabaster):** The main background color, providing a clean, warm canvas that feels more premium than standard white.

Use a monochromatic "Chocolate" scale for functional states (hover/active) to maintain the organic aesthetic.

## Typography

Typography is the cornerstone of this design system. We use a high-contrast serif for a literary, editorial feel and a clean sans-serif for functional clarity.

- **Headlines:** Use *Playfair Display*. For names or dramatic statements, use the `script-accent` style (Italic) to mimic the fluidity of calligraphy.
- **Body & Labels:** Use *Libre Franklin*. Its neutral, slightly wider stance balances the decorative nature of the serif.
- **Letter Spacing:** Headlines should have slight tracking (tightened for large sizes, expanded for sub-headers) to evoke professional typesetting.

## Layout & Spacing

The layout follows a **Fixed Grid** model centered on the screen, mimicking the physical constraints of a printed invitation card.

- **The Arch Motif:** Content should frequently be housed within a "pill-top" or arched container. This creates an architectural frame that feels more intentional than a standard rectangle.
- **Rhythm:** Use a strict 8px baseline grid. Large vertical gaps (80px+) between sections are encouraged to maintain a minimalist, "breathable" feel.
- **Mobile:** On mobile devices, margins should remain generous (24px) to ensure the decorative floral elements or borders do not crowd the central text.

## Elevation & Depth

This system avoids heavy drop shadows in favor of **Tonal Layering** and **Soft Insets**.

- **Depth:** Create hierarchy by stacking shades of Alabaster and Sand. An arched card sitting on a Terracotta background creates depth through color contrast rather than shadow.
- **Micro-Shadows:** If a shadow is required for a floating button, use a very diffused, low-opacity shadow tinted with the Tertiary Brown color (`rgba(74, 50, 40, 0.08)`).
- **Masking:** Use the arch shape as a mask for photography or floral illustrations to create a "contained" organic look.

## Shapes

The shape language is defined by the **Arch**. 

- **Primary Container:** Use a custom radius where the top corners are fully rounded (pill-shaped) while the bottom corners remain square or slightly rounded (8px).
- **UI Elements:** Buttons and input fields should use a `rounded-lg` (16px) or fully pill-shaped profile to contrast with the sharp elegance of the serif type.
- **Dividers:** Use thin (1px), low-opacity lines in Tertiary Brown to separate sections without breaking the visual flow.

## Components

- **Primary Button:** Solid Terracotta background with Alabaster text. Use uppercase `label-sm` typography with 0.1em letter spacing.
- **Secondary Button:** Outlined in Tertiary Brown with a 1px border. No fill.
- **Cards:** Arched top-edge containers. Backgrounds should be Alabaster or Soft Sand. 
- **Input Fields:** Bottom-border only or very soft-tinted backgrounds. Avoid heavy boxes.
- **Floral Accents:** Use botanical illustrations (roses, leaves) as "bleed" elements that overlap the edges of containers, breaking the grid slightly to provide a romantic, organic touch.
- **Countdown/Date:** Center-aligned, using `headline-md` with wide tracking to emphasize the importance of the event date.