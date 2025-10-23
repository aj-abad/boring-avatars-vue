<script setup lang="ts">
import AvatarBauhaus from '@/lib/components/AvatarBauhaus.vue'
import AvatarBeam from '@/lib/components/AvatarBeam.vue'
import AvatarMarble from '@/lib/components/AvatarMarble.vue'
import AvatarPixel from '@/lib/components/AvatarPixel.vue'
import AvatarRing from '@/lib/components/AvatarRing.vue'
import AvatarSunset from '@/lib/components/AvatarSunset.vue'
</script>

<template>
  <div style="display: flex; gap: 1rem">
    <avatar-bauhaus
      name="dev@ajabad.com"
      :colors="['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']"
      size="50"
    />
    <avatar-beam
      name="dev@ajabad.com"
      :colors="['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']"
      size="50"
    />
    <avatar-marble
      name="dev@ajabad.com"
      :colors="['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']"
      size="50"
    />
    <avatar-pixel
      name="dev@ajabad.com"
      :colors="['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']"
      size="50"
    />
    <avatar-ring
      name="dev@ajabad.com"
      :colors="['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']"
      size="50"
    />
    <avatar-sunset
      name="dev@ajabad.com"
      :colors="['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']"
      size="50"
    />
  </div>
</template>

<style scoped></style>
