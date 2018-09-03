<template>
    <div>
       <table>
          <colgroup>
            <col v-if="hasCheckbox" style="width:40px"/>
            <col v-for="(head, index) in header" :key="index" style="width:200px">
          </colgroup>
          <thead>
            <tr>
              <th v-if="hasCheckbox">
                  <input type="checkbox"/>
              </th>
              <th v-for="(head, index) in header" :key="index"
              >{{head.name}}</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(item, index) in realItems" :key="index">
                <td v-if="hasCheckbox">
                    <input type="checkbox" :value="item" v-model="selected" @change="onClickCheckbox"/>
                </td>
                <td v-for="(head, index) in header" :key="index">
                    <input v-if="head.type === 'input'" v-model="item[head.name]" />
                    <select v-else-if="head.type === 'select'" v-model="item[head.name]">
                        <option v-for="(option, index) in head.options" :key="index" :value="option.value">
                            {{ option.text }}
                        </option>
                    </select>
                    <div v-else>{{ item[head.name]}}</div>
                </td>
            </tr>
          </tbody>
       </table>
       {{ selected }}
       <br>
       {{ realItems }}
    </div>
</template>
<script>
export default {
  name: 'DataTable',
  props: {
    header: {
      type: Array,
      default: () => []
    },
    items: {
      type: Array,
      default: () => []
    },
    hasCheckbox: {
      type: Boolean,
      default: false
    }
  },
  data () {
    return {
      selected: [],
      realItems: []
    }
  },
  created () {
    this.realItems = this.items
  },
  methods: {
    onClickCheckbox () {
      this.$emit('clickCheckbox', this.selected)
    }
  }
}
</script>
<style>
table th {
    border: 1px;
}
</style>
