<template>
  <span @click="switchFilter(id, from, to)">
    <button
      class="relative brdr-cl-bg-tertiary brdr-1 bg-cl-transparent mr10 pointer price-button"
      :class="{ active: active }"
      :aria-label="$t('Price ') + content"
    >
      <div class="bg-cl-transparent absolute block square"/>
    </button>
    <span>{{ content }}</span>
  </span>
</template>

<script>
import { coreComponent } from 'core/lib/themes'

export default { // TODO: move logic to parent component
  mixins: [coreComponent('PriceButton')]
}
</script>

<style lang="scss" scoped>
  @import '~theme/css/variables/colors';
  @import '~theme/css/helpers/functions/color';
  $color-event: color(tertiary);
  $color-active: color(accent);

  .price-button {
    width: 20px;
    height: 20px;

    &:hover,
    &:focus {
      .square {
        background-color: $color-event;
      }
    }

    &.active {
      .square {
        background-color: $color-active;
      }
    }
  }

  .square {
    width: 80%;
    height: 80%;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
  }
</style>
