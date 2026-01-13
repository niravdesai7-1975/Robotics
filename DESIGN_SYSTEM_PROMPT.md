# Design System Prompt - Minimalist Monochrome

Use this prompt to apply the same clean, minimalist monochrome design system to any website project.

## Color Scheme

### Background Colors
- **Primary Background**: Pure white `#ffffff` (`bg-white` in Tailwind)
- **No gradients, no color variations** - maintain pure white throughout all sections
- **Placeholder backgrounds**: Light gray `bg-gray-100` for media placeholders

### Text Colors
- **Headings**: Pure black `#000000` (`text-black` in Tailwind) or very dark gray
- **Body Text**: Dark gray `#333333` (`text-dark-gray`) or `#444444` (`text-darker-gray`)
- **Placeholder Text**: Medium gray `#6b7280` (`text-gray-500`)
- **No accent colors** - strictly neutral monochrome palette only
- **No colored text** - avoid blues, greens, reds, or any colored accents

### Border Colors (for placeholders)
- **Border**: Light gray `#d1d5db` (`border-gray-300`)
- **Border Style**: Dashed (`border-dashed`) for placeholders

## Typography

### Font Family
- **Primary Font**: Google Font "Inter"
- **Weights Available**: 400 (regular), 500 (medium), 600 (semibold), 700 (bold), 800 (extrabold), 900 (black)
- **Font Loading**: Use preconnect for performance:
  ```html
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  ```

### Typography Scale

#### Hero Text
- **Desktop**: `text-7xl` to `text-9xl` (72px - 128px)
- **Tablet**: `text-8xl` (96px)
- **Mobile**: `text-7xl` (72px)
- **Weight**: `font-black` (900)
- **Line Height**: `leading-tight`
- **Spacing**: Large margins between lines (`mb-8`)

#### Section Titles
- **Desktop**: `text-4xl` to `text-5xl` (36px - 48px)
- **Mobile**: `text-4xl` (36px)
- **Weight**: `font-bold` (700)
- **Color**: Pure black `#000000`

#### Subheadings
- **Size**: `text-2xl` to `text-3xl` (24px - 30px)
- **Weight**: `font-semibold` (600)

#### Body Text
- **Size**: `text-lg` to `text-xl` (18px - 20px)
- **Weight**: `font-normal` (400)
- **Line Height**: `leading-relaxed`
- **Color**: Dark gray `#333333` or `#444444`

#### Emphasized Text
- **Size**: `text-2xl` to `text-3xl` (24px - 30px)
- **Weight**: `font-bold` (700) and `italic`
- **Color**: Pure black `#000000`

## Layout & Spacing

### Container Widths
- **Hero**: `max-w-5xl` (1024px)
- **Content Sections**: `max-w-4xl` (896px) to `max-w-5xl` (1024px)
- **Wide Sections**: `max-w-6xl` (1152px) for media-heavy sections
- **Centering**: Always use `mx-auto` to center containers

### Vertical Spacing
- **Between Major Sections**: `py-32` to `py-64` (128px - 256px)
- **Section Padding**: `px-4` for mobile, responsive padding
- **Hero Section**: `min-h-screen` with `py-32` for full viewport height minus padding
- **Content Spacing**: Generous breathing room between elements

### Horizontal Spacing
- **Mobile Padding**: `px-4` (16px)
- **Content Padding**: Responsive, minimal on mobile, comfortable on desktop

## Design Philosophy

### Minimalism
- **No header navigation** - ultra-minimalist approach
- **No footer clutter** - clean, content-focused
- **No decorative elements** - pure content only
- **No icons** unless absolutely necessary
- **No colored accents** - monochrome only

### Content Focus
- **Centered alignment** - all content strictly centered
- **Large typography** - bold, impactful text
- **Generous whitespace** - let content breathe
- **Clear hierarchy** - use size and weight, not color

### Responsiveness
- **Mobile-first** - text scales down gracefully
- **Aspect ratios maintained** - use `aspect-video` for media placeholders
- **Flexible containers** - max-width constraints with auto margins
- **Responsive text sizes** - use Tailwind breakpoints (`md:`, `lg:`)

## Media Placeholders

### Standard Video Placeholder (16:9)
```html
<div class="w-full max-w-5xl mx-auto aspect-video bg-gray-100 border-2 border-dashed border-gray-300 rounded-2xl flex items-center justify-center my-16">
    <span class="text-gray-500 text-xl md:text-2xl text-center px-8">
        [Description]<br>
        (16:9 Video Placeholder)
    </span>
</div>
```

### Large Hero Video Placeholder
```html
<div class="w-full max-w-6xl mx-auto h-[70vh] md:h-[80vh] min-h-[500px] bg-gray-100 border-2 border-dashed border-gray-300 rounded-2xl flex items-center justify-center my-20">
    <span class="text-gray-500 text-2xl md:text-3xl text-center px-8">
        [Description]<br>
        (Large Responsive Placeholder)
    </span>
</div>
```

### Logo Placeholder Grid
```html
<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-12 my-20">
    <div class="w-48 h-24 bg-gray-100 border-2 border-dashed border-gray-300 rounded-xl flex items-center justify-center mx-auto">
        <span class="text-gray-500 text-sm">Partner Logo</span>
    </div>
    <!-- Repeat as needed -->
</div>
```

## Animations

### Scroll Animations
- **Library**: AOS (Animate On Scroll) - `https://unpkg.com/aos@2.3.1/dist/aos.css`
- **Effect**: `fade-up` (subtle fade-in from bottom)
- **Duration**: 800ms
- **Easing**: `ease-in-out`
- **Trigger**: Once per element (`once: true`)
- **Offset**: 100px before triggering

### Implementation
```html
<!-- Add to sections -->
<div data-aos="fade-up">
    <!-- content -->
</div>

<!-- Initialize -->
<script>
    AOS.init({
        duration: 800,
        easing: 'ease-in-out',
        once: true,
        offset: 100
    });
</script>
```

## Tailwind CSS Configuration

### Custom Colors
```javascript
tailwind.config = {
    theme: {
        extend: {
            colors: {
                'dark-gray': '#333333',
                'darker-gray': '#444444',
            }
        }
    }
}
```

## Quick Reference Checklist

When applying this design system:

- [ ] Pure white background (`#ffffff`) throughout
- [ ] Black headings (`#000000`)
- [ ] Dark gray body text (`#333333` or `#444444`)
- [ ] Google Font "Inter" loaded with all weights
- [ ] Hero text: `text-7xl` to `text-9xl`, `font-black`
- [ ] Section titles: `text-4xl` to `text-5xl`, `font-bold`
- [ ] Body text: `text-lg` to `text-xl`, `leading-relaxed`
- [ ] Generous vertical spacing (`py-32` to `py-64`)
- [ ] Centered content with max-width containers
- [ ] No colored accents - monochrome only
- [ ] Subtle AOS fade-up animations
- [ ] Responsive text scaling with Tailwind breakpoints
- [ ] Aspect-ratio maintained placeholders for media

## Example Usage Prompt

```
Create a website using this design system:
- Background: Pure white #ffffff
- Headings: Black #000000, extremely large (text-7xl to text-9xl for hero)
- Body text: Dark gray #333333, text-lg to text-xl
- Font: Google Font "Inter" (weights 400-900)
- Layout: Centered content, max-w-4xl to max-w-6xl containers
- Spacing: py-32 to py-64 between sections
- No header/footer, no accent colors, ultra-minimalist
- Subtle AOS fade-up animations on scroll
- Responsive with Tailwind CSS breakpoints
```


