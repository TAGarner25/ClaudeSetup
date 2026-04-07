---
name: erickson-brand-guidelines
description: Applies Erickson Group's official brand colors and typography to any sort of work-related artifact. Use it when brand colors or style guidelines, visual formatting, or company design standards apply. Examples of artifacts include pdf's, powerpoint presentations, or similar documents.
author: Trevor Garner
---

# Erickson Group Brand Styling

## Overview

To access Erickson Groups's official brand identity and style resources, use this skill.

**Keywords**: branding, corporate identity, visual identity, post-processing, styling, brand colors, typography, Erickson Group brand, visual formatting, visual design, company branding

## Brand Guidelines

### Colors

**Main Colors:**

- Midnight Steel: `#1A2332` - Primary backgrounds, headers, hero sections, navigation bar
- Timber Green: `#2B4C3F` - Secondary backgrounds, section dividers, CTA buttons, accents
- Dark Text: `#18181b` - Primary dark text and dark backgrounds
- Warm White: `#FAF8F5` - Light backgrounds and text on dark backgrounds
- Slate Grey: `#6B7B8D` - Secondary text, captions, muted UI elements, metadata, and subtle backgrounds
- Stone: `#D4CCC0` - Borders, dividers, card backgrounds, subtle separators

**Accent Colors:**

- Copper Heritage: `#C17F3E` - Alternate primary accent
- Blazing Orange: `#FF5D00` - Primary accent
- Blue: `#6a9bcc` - Secondary accent
- Green: `#2B4C3F` - Tertiary accent

**Color Ratios:**

- For balanced compositions, apply the following approximate ratios across all layouts: 40% Midnight Steel (dominant structure), 20% Timber Green (supporting depth), 10% Blazing Orange or Copper Heritage (accent and emphasis), 30% Parchment/Warm White (breathing room and content areas).
- Never allow Copper Heritage to exceed 15% of any layout. It is an accent — not a primary.
- Timber Green and Midnight Steel can be interchanged as the dominant depending on context, but one must always lead.

### Typography

- **Titles**: Libre Baskerville (with Georgia fallback)
- **Headings**: Poppins (with Aptos Display fallback)
- **Body Text**: Lora (with Aptos fallback)
- **Note**: Fonts should be pre-installed in your environment for best results

## Features

### Smart Font Application

- Applies Libre Baskerville front to titles and headers or when "Erickson Group" is used as a string logo
- Applies Poppins font to headings (24pt and larger)
- Applies Lora font to body text
- Automatically falls back to Aptos/Aptos Display/Georgia if custom fonts unavailable
- Preserves readability across all systems

### Text Styling

- Headings (24pt+): Poppins font
- Body text: Lora font
- Smart color selection based on background
- Preserves text hierarchy and formatting

### Shape and Accent Colors

- Non-text shapes use accent colors
- Uses color ratios defined in the Colors section
- Maintains visual interest while staying on-brand

## Technical Details

### Font Management

- Uses system-installed Poppins and Lora fonts when available
- Provides automatic fallback to Aptos Display (headings), Aptos (body), and Georgia (titles)
- No font installation required - works with existing system fonts
- For best results, pre-install Poppins and Lora fonts in your environment

### Color Application

- Uses RGB color values for precise brand matching
- Applied via python-pptx's RGBColor class
- Maintains color fidelity across different systems