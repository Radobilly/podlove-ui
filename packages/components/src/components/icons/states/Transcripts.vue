<template>
  <svg
    :width="size"
    :height="size"
    viewBox="0 0 24 24"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <line
      x1="15.45"
      y1="13.45"
      x2="8.55"
      y2="13.45"
      :stroke="color"
      stroke-width="1.1"
      stroke-linecap="round"
    />
    <line
      x1="15.45"
      y1="16.45"
      x2="8.55"
      y2="16.45"
      :stroke="color"
      stroke-width="1.1"
      stroke-linecap="round"
    />
    <line
      x1="15.45"
      y1="10.45"
      x2="8.55"
      y2="10.45"
      :stroke="color"
      stroke-width="1.1"
      stroke-linecap="round"
    />
    <line
      x1="11.45"
      y1="7.45002"
      x2="8.55"
      y2="7.45002"
      :stroke="color"
      stroke-width="1.1"
      stroke-linecap="round"
    />
    <path
      d="M5.55 3.55H14.7722L18.45 7.22782V19.45H5.55V3.55Z"
      :stroke="color"
      stroke-width="1.1"
    />
    <path
      d="M14.5 3.5V6.75C14.5 7.16421 14.8358 7.5 15.25 7.5H18.5"
      :stroke="color"
      stroke-width="1.1"
    />
  </svg>
</template>

<script>
export default {
  props: {
    size: {
      type: Number,
      default: 24
    },
    color: {
      type: String,
      default: 'currentColor'
    }
  }
}
</script>
