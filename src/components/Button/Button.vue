<template>
  <div>
    <button>{{ label }}</button>
  </div>
</template>
<script>
export default {
  name: 'test-button',
  props: {
    label: {
      type: String
    }
  }
}
</script>
