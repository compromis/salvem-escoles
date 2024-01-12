<script setup>
const props = defineProps({
  to: {
    type: Number,
    required: true
  },
  from: {
    type: Number,
    default: 0
  },
  append: {
    type: String,
    default: ''
  },
  duration: {
    type: Number,
    default: 1.25
  }
})

const { $gsap } = useNuxtApp()
const animatedNumber = ref(null)

const numberFormat = (number) => {
  return number.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".")
}

onMounted(() => {
  $gsap.from(animatedNumber.value, {
    textContent: props.from,
    duration: props.duration,
    snap: { textContent: 1 },
    stagger: 1,
    ease: 'Power1.easeIn',
    scrollTrigger: {
      trigger: animatedNumber.value,
      start: 'top bottom'
    },
    onUpdate: function() {
      this.targets()[0].innerHTML = `${numberFormat(Math.ceil(this.targets()[0].textContent))}${props.append}`
    },
  })
})
</script>

<template>
  <span class="animated-number" ref="animatedNumber">
    {{ to }}
  </span>
</template>

<style lang="scss" scoped>
.animated-number {
  font-variant-numeric: tabular-nums;
  white-space: nowrap;
}
</style>