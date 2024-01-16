<script setup>
const video = ref()

const { playing, currentTime, duration } = useMediaControls(video, {
  src: '/video/intro.mp4'
})

const progress = computed(() => {
  return currentTime.value * 100 / duration.value
})
</script>

<template>
  <div :class="['video-player', { playing }]">
    <video loop playsinline ref="video" @click="playing = !playing" />
    <button class="play" @click="playing = !playing">
      <template v-if="playing">
        <IconPause />
        {{ $t('video.pause') }}
      </template>
      <template v-else>
        <IconPlay />
        {{ $t('video.play') }}
      </template>
    </button>

    <div class="progress">
      <div class="progress-track" :style="{ width: progress + '%' }" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.video-player {
  display: flex;
  position: relative;

  video {
   width: 100%;
   height: 100%;
   object-fit: fill;
   cursor: pointer;
  }

  .play {
    position: absolute;
    appearance: none;
    background: var(--yellow);
    color: var(--blue);
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%) scale(var(--scale, 1));
    font-weight: bold;
    border: 0;
    border-radius: 10rem;
    padding: 1rem 1.5rem;
    display: flex;
    align-items: center;
    gap: .5rem;
    font-size: var(--text-lg);
    transition: .5s ease;

    :deep(svg) {
      height: 1em;
      width: 1em;
    }
  }

  &.playing {
    .play {
      opacity: 0;
      top: .75rem;
      left: .75rem;
      transform: translate(0, 0);
      padding: .5rem 1rem;
      font-size: var(--text-md);
      border-radius: .75rem;
    }

    &:hover .play {
      opacity: 1;
    }
  }

  &:hover .play {
    --scale: 1.1;
  }
}

.progress {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: .75rem;
  pointer-events: none;

  &-track {
    height: .75rem;
    background-color: var(--yellow);
    border-radius: 4rem;
    transition: .5s linear;
  }
}
</style>