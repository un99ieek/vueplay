<template>
  <div>
    <resizable />
  </div>
</template>
<script>
import {TimePicker as aa} from './TimePicker'
import Resizable from './Resizable'
import Btn from './Button'
export default {
  name: 'playground',
  components: { aa, Btn, Resizable }
}
</script>
