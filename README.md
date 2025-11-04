# @karlorz/image-annotate

A React component library for image annotation with support for bounding boxes, polygons, points, and more. Built with React, TypeScript, Vite, and Tailwind CSS.

## Features

- 🎨 Canvas-based drawing tools for annotations
- 📦 Support for multiple annotation formats (COCO, YOLO, custom JSON)
- 🖼️ Image display with zoom and pan controls
- 🛠️ Customizable annotation tools (select, draw, erase)
- 📝 Label management and metadata support
- ⚛️ Built with React 19 and TypeScript
- 🎭 Storybook for component development and documentation
- 🎨 Styled with Tailwind CSS 4
- ⚡ Fast builds with Vite

## Installation

```bash
npm install @karlorz/image-annotate
```

or

```bash
yarn add @karlorz/image-annotate
```

## Usage

```tsx
import { ImageAnnotator } from '@karlorz/image-annotate';
import '@karlorz/image-annotate/styles.css';

function App() {
  return (
    <ImageAnnotator
      image="/path/to/image.jpg"
      onAnnotationsChange={(annotations) => {
        console.log('Annotations updated:', annotations);
      }}
    />
  );
}
```

## Development

### Prerequisites

- Node.js 22+
- npm 10+

### Setup

```bash
# Clone the repository
git clone https://github.com/karlorz/image-annotate.git
cd image-annotate

# Install dependencies
npm install

# Start Storybook development server
npm run dev
```

### Available Scripts

- `npm run dev` - Start Storybook development server
- `npm run build` - Build Storybook for production
- `npm run build:lib` - Build the component library
- `npm run test` - Run tests in watch mode
- `npm run test:cov` - Run tests with coverage
- `npm run lint` - Lint the codebase
- `npm run format` - Format code with Biome

## Component Architecture

The library follows the Atomic Design methodology:

- **Atoms** - Basic building blocks (buttons, inputs)
- **Molecules** - Simple combinations of atoms
- **Organisms** - Complex UI components

## Publishing

This project uses [Release Please](https://github.com/googleapis/release-please) for automated versioning and changelog generation.

### Automated Release Process

1. Make your changes and push to main
2. Release Please will automatically create/update a PR with version bumps
3. Merge the Release Please PR when ready to release
4. GitHub Actions will automatically:
   - Create a GitHub release
   - Build and test the library
   - Publish to npm

### Manual Publishing

If you need to publish manually:

1. Update the version in `package.json`
2. Build the library: `npm run build:lib`
3. Publish to npm: `npm publish --access public` (first time only, then `npm publish`)

For scoped packages, the first publish requires `--access public`.

## License

MIT © karlorz

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

For issues and feature requests, please use the [GitHub issues page](https://github.com/karlorz/image-annotate/issues).