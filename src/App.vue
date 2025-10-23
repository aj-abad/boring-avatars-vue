<script setup lang="ts">
import AvatarBauhaus from '@/lib/components/AvatarBauhaus.vue'
import AvatarBeam from '@/lib/components/AvatarBeam.vue'
import AvatarMarble from '@/lib/components/AvatarMarble.vue'
import AvatarPixel from '@/lib/components/AvatarPixel.vue'
import AvatarRing from '@/lib/components/AvatarRing.vue'
import AvatarSunset from '@/lib/components/AvatarSunset.vue'
const colors = ['#92A1C6', '#146A7C', '#F0AB3D', '#C271B4', '#C20D90']
const name = 'dev@ajabad.com'
</script>

<template>
  <div style="display: flex; gap: 1rem">
    <avatar-bauhaus
      :name="name"
      :colors="colors"
      size="50"
    />
    <avatar-beam
      :name="name"
      :colors="colors"
      size="50"
    />
    <avatar-marble
      :name="name"
      :colors="colors"
      size="50"
    />
    <avatar-pixel
      :name="name"
      :colors="colors"
      size="50"
    />
    <avatar-ring
      :name="name"
      :colors="colors"
      size="50"
    />
    <avatar-sunset
      :name="name"
      :colors="colors"
      size="50"
    />
  </div>
</template>

<style scoped></style>
