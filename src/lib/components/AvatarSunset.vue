<script setup lang="ts">
import { computed } from 'vue'
import { hashCode, getRandomColor } from '../utilities'

interface Props {
  name: string
  colors: string[]
  title?: boolean
  square?: boolean
  size?: string | number
}

const props = defineProps<Props>()

const ELEMENTS = 4
const SIZE = 80

function generateColors(name: string, colors: string[]) {
  const numFromName = hashCode(name)
  const range = colors && colors.length

  const colorsList = Array.from({ length: ELEMENTS }, (_, i) =>
    getRandomColor(numFromName + i, colors, range),
  )

  return colorsList
}

const sunsetColors = computed(() => generateColors(props.name, props.colors))
const nameWithoutSpace = computed(() => props.name.replace(/\s/g, ''))
const maskID = computed(() => `mask-${hashCode(props.name)}`)
const gradientId0 = computed(() => `gradient_paint0_linear_${nameWithoutSpace.value}`)
const gradientId1 = computed(() => `gradient_paint1_linear_${nameWithoutSpace.value}`)
</script>

<template>
  <svg
    :viewBox="`0 0 ${SIZE} ${SIZE}`"
    fill="none"
    role="img"
    xmlns="http://www.w3.org/2000/svg"
    :width="size"
    :height="size"
  >
    <title v-if="title">{{ name }}</title>
    <mask :id="maskID" maskUnits="userSpaceOnUse" :x="0" :y="0" :width="SIZE" :height="SIZE">
      <rect :width="SIZE" :height="SIZE" :rx="square ? undefined : SIZE * 2" fill="#FFFFFF" />
    </mask>
    <g :mask="`url(#${maskID})`">
      <path :fill="`url(#${gradientId0})`" d="M0 0h80v40H0z" />
      <path :fill="`url(#${gradientId1})`" d="M0 40h80v40H0z" />
    </g>
    <defs>
      <linearGradient
        :id="gradientId0"
        :x1="SIZE / 2"
        :y1="0"
        :x2="SIZE / 2"
        :y2="SIZE / 2"
        gradientUnits="userSpaceOnUse"
      >
        <stop :stop-color="sunsetColors[0]" />
        <stop offset="1" :stop-color="sunsetColors[1]" />
      </linearGradient>
      <linearGradient
        :id="gradientId1"
        :x1="SIZE / 2"
        :y1="SIZE / 2"
        :x2="SIZE / 2"
        :y2="SIZE"
        gradientUnits="userSpaceOnUse"
      >
        <stop :stop-color="sunsetColors[2]" />
        <stop offset="1" :stop-color="sunsetColors[3]" />
      </linearGradient>
    </defs>
  </svg>
</template>
