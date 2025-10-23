# Publishing to NPM

This guide will help you publish the boring-avatars-vue package to npm.

## Prerequisites

1. **Create an npm account**: If you don't have one, create an account at [npmjs.com](https://www.npmjs.com/signup)

2. **Login to npm**: Run the following command and enter your credentials:
   ```bash
   npm login
   ```

## Publishing Steps

### 1. Update Version (if needed)

Before publishing, update the version in `package.json` following [semantic versioning](https://semver.org/):

```bash
# For a patch release (bug fixes)
npm version patch

# For a minor release (new features, backward compatible)
npm version minor

# For a major release (breaking changes)
npm version major
```

### 2. Build the Library

The build will automatically run before publishing (via `prepublishOnly` script), but you can test it manually:

```bash
npm run build
```

This will:
- Run TypeScript type checking
- Build the ES module and UMD bundles
- Generate TypeScript declaration files

### 3. Test the Package Locally

Before publishing, test the package locally:

```bash
# Create a tarball
npm pack

# This creates a file like boring-avatars-vue-1.0.0.tgz
# You can install it in another project to test:
# npm install /path/to/boring-avatars-vue-1.0.0.tgz
```

### 4. Publish to npm

Once you're ready to publish:

```bash
npm publish
```

For the first time publishing, you might need to make the package public:

```bash
npm publish --access public
```

### 5. Verify the Publication

After publishing, verify your package:

1. Visit: `https://www.npmjs.com/package/boring-avatars-vue`
2. Install in a test project: `npm install boring-avatars-vue`
3. Test the imports work correctly

## What Gets Published

The `files` field in `package.json` specifies what gets included:
- `dist/` - The compiled library files
- `README.md` - Documentation
- `LICENSE` - License file

The `.npmignore` file excludes:
- Source files (`src/`)
- Configuration files
- Development dependencies
- Test files

## Post-Publishing

1. **Create a Git tag**: If you used `npm version`, a tag is already created. Push it:
   ```bash
   git push --tags
   ```

2. **Create a GitHub release**: Go to your repository's releases page and create a new release from the tag.

3. **Update documentation**: Make sure the README and any other docs reflect the latest changes.

## Updating the Package

To publish updates:

1. Make your changes
2. Update the version: `npm version patch/minor/major`
3. Publish: `npm publish`
4. Push changes: `git push && git push --tags`

## Troubleshooting

### "You do not have permission to publish"
- Make sure you're logged in: `npm whoami`
- Check if the package name is already taken
- Use `--access public` flag

### "Package name too similar to existing package"
- npm might reject names too similar to existing packages
- Choose a more unique name if necessary

### Build errors
- Ensure all dependencies are installed: `npm install`
- Check TypeScript errors: `npm run type-check`
- Clear the dist folder and rebuild: `rm -rf dist && npm run build`

## Unpublishing (Use with Caution)

If you need to unpublish within 72 hours of publishing:

```bash
npm unpublish boring-avatars-vue@<version>
```

**Warning**: Unpublishing is permanent and can break projects depending on your package. Only use in case of serious security issues or mistakes.
