# AGENTS.md

This file provides guidance to Coding Agents when working with code in this repository.

## Project Overview

This is an image annotation component library built with React, TypeScript, Vite, and Tailwind CSS. Published as `@karlorz/image-annotate` on npm.

## IMPORTANT RULES

### Publishing & Versioning
1. **NEVER** publish to npm without explicit user permission
2. **ALWAYS** run tests before building the library (`npm run test:cov`)
3. **ALWAYS** increment version in package.json before publishing (follow semver)
4. For first publish of scoped package, use: `npm publish --access public`
5. Subsequent publishes only need: `npm publish`

### Code Quality
1. **ALWAYS** use TypeScript for new components
2. **ALWAYS** include tests for new components (*.test.tsx files)
3. **ALWAYS** create Storybook stories for visual components (*.stories.tsx files)
4. **ALWAYS** run linter before committing: `npm run lint`
5. **NEVER** commit with failing tests

### Component Development
1. Follow Atomic Design pattern strictly:
   - Atoms: `at-*` prefix (basic elements)
   - Molecules: `ml-*` prefix (combinations of atoms)
   - Organisms: `or-*` prefix (complex components)
2. Export all new components through the appropriate index.ts file
3. Use Tailwind CSS for styling, avoid inline styles
4. Make components fully typed with proper TypeScript interfaces

### Image Annotation Specific
1. Canvas operations should be performant and use requestAnimationFrame when needed
2. Support standard annotation formats (COCO, YOLO, custom JSON)
3. Annotations should be serializable/deserializable
4. Include undo/redo functionality for annotation operations
5. Handle large images efficiently with virtualization if needed

## Development Commands

### Core Development
- `npm run dev` - Start Storybook development server on port 6006
- `npm run build:lib` - Build the component library for distribution (outputs to dist/)
- `npm run build` - Build the static Storybook site

### Testing
- `npm test` - Run tests in watch mode using Vitest
- `npm run test:cov` - Run tests once with coverage report
- Run a single test: `npm test -- path/to/test.tsx`

### Code Quality
- `npm run lint` - Run Biome linter
- `npm run format` - Format code and organize imports using Biome

### Publishing
- `npm run build:lib` - Build before publishing
- `npm publish --access public` - First time publishing scoped package
- `npm publish` - Subsequent publishes

### Prerequisites
- Node.js 22+ required
- npm 10+ required
- `npm install` to install dependencies

## Architecture

### Component Structure (Atomic Design)
The library follows Atomic Design methodology with three component levels:

- **Atoms** (`src/lib/components/atoms/`) - Basic building blocks
- **Molecules** (`src/lib/components/molecules/`) - Simple combinations of atoms
- **Organisms** (`src/lib/components/organisms/`) - Complex UI components

### Build Configuration
- **Library Entry**: `src/lib/index.ts` - Main entry point that exports all components and imports Tailwind theme
- **Vite Config**: `vite.config.mts` - Builds both ES and UMD formats, with React as external dependency
- **Library Name**: `ImageAnnotate` (global variable for UMD)
- **Output Files**:
  - `dist/image-annotate.es.js` (ES module)
  - `dist/image-annotate.umd.js` (UMD)
  - `dist/index.d.ts` (TypeScript definitions)
  - `dist/image-annotate.css` (Styles)
- **Storybook**: Separate Vite config in `.storybook/vite.config.ts` for isolated Storybook builds

### Testing Strategy
- Component tests use Vitest with React Testing Library
- Test files colocated with components as `*.test.tsx`
- Coverage excludes Storybook files and configs
- Run `npm run test:cov` before any release

### Styling
- Tailwind CSS 4 with configuration in `tailwind.config.js`
- Theme CSS imported at library entry point (`src/lib/tailwind/theme.css`)
- PostCSS configured with Tailwind and Autoprefixer

## Image Annotation Components Roadmap

Priority components to implement:

1. **ImageCanvas** - Base canvas component for displaying images
2. **BoundingBoxTool** - Tool for drawing rectangular annotations
3. **PolygonTool** - Tool for drawing polygon annotations
4. **PointTool** - Tool for marking point annotations
5. **SelectionTool** - Tool for selecting and editing existing annotations
6. **ZoomPanControls** - Controls for zooming and panning the canvas
7. **AnnotationList** - Component to display and manage annotation list
8. **LabelSelector** - Component for selecting annotation labels/classes
9. **ExportPanel** - Component for exporting annotations in various formats
10. **ImageAnnotator** - Main wrapper component combining all tools

## Package Distribution

The library is published to npm as `@karlorz/image-annotate`:
- Scoped package under @karlorz namespace
- Main entry: `dist/image-annotate.umd.js`
- Module entry: `dist/image-annotate.es.js`
- TypeScript definitions: `dist/index.d.ts`
- CSS export: `dist/image-annotate.css`

GitHub repository: https://github.com/karlorz/image-annotate