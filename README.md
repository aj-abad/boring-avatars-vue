# Boring Avatars Vue

Boring avatars is a tiny JavaScript Vue 3 library that generates custom, SVG-based avatars from any username and color palette.

<a href="https://www.npmjs.com/package/boring-avatars-vue">

![npm version](https://badgen.net/npm/v/boring-avatars-vue)

</a>

## Install

```bash
npm install boring-avatars-vue
```

## Usage

```vue
<script setup>
import { AvatarBeam } from 'boring-avatars-vue'
</script>

<template>
  <AvatarBeam name="Maria Mitchell" />
</template>
```

### Available Components

```vue
<script setup>
import { 
  AvatarBeam,
  AvatarBauhaus,
  AvatarMarble,
  AvatarPixel,
  AvatarRing,
  AvatarSunset
} from 'boring-avatars-vue'
</script>
```

### Props

| Prop    | Type             | Default                                                   |
|---------|------------------|-----------------------------------------------------------|
| size    | number or string | `40`                                                      |
| square  | boolean          | `false`                                                   |
| title   | boolean          | `false`                                                   |
| name    | string           | `Clara Barton`                                            |
| colors  | string[]         | `['#92A1C6', '#146A7C', '#F0AB3D', '#C271B4', '#C20D90']` | 


#### Name
The `name` prop is used to generate the avatar. It can be the username, email or any random string.

```vue
<AvatarBeam name="Maria Mitchell" />
```

#### Variants
Use different components for different avatar styles:

```vue
<AvatarBeam name="Alice Paul" />
<AvatarBauhaus name="Alice Paul" />
<AvatarMarble name="Alice Paul" />
<AvatarPixel name="Alice Paul" />
<AvatarRing name="Alice Paul" />
<AvatarSunset name="Alice Paul" />
```

#### Size
The `size` prop is used to change the size of the avatar.

```vue
<AvatarBeam name="Ada Lovelace" :size="88" />
```

#### Colors
The `colors` prop is used to change the color palette of the avatar.

```vue
<AvatarBeam 
  name="Grace Hopper" 
  :colors="['#fb6900', '#f63700', '#004853', '#007e80', '#00b9bd']" 
/>
```

#### Square
The `square` prop is used to make the avatar square.

```vue
<AvatarBeam name="Helen Keller" square />
```

#### Title
The `title` prop adds a title element to the SVG for accessibility.

```vue
<AvatarBeam name="Katherine Johnson" title />
```

## TypeScript Support

This library is written in TypeScript and includes type definitions.

## Credits

This is a Vue 3 port of the original [boring-avatars](https://github.com/boringdesigners/boring-avatars) React library by [Boring Designers](https://boringavatars.com).

## License

MIT
