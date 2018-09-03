<template>
  <div>
    <data-table :header="header" :items="items" :hasCheckbox="true"
     @clickCheckbox="onClickCheckbox"/>
  </div>
</template>
<script>
import {TimePicker as aa} from './TimePicker'
import DataTable from './DataTable'
import Resizable from './Resizable'
import Btn from './Button'
export default {
  name: 'playground',
  components: { aa, Btn, Resizable, DataTable },
  data () {
    return {
      header: [
        {name: 'first name'},
        {name: 'last name', type: 'input'},
        {name: 'dept', type: 'select', options: [{text: 'dept1', value: '1'}, {text: 'dept2', value: '2'}, {text: 'dept3', value: '3'}]},
        {name: 'address'}
      ],
      items: [
        {'first name': 'doe', 'last name': 'kim', 'dept': '1', 'address': 'addr11111'},
        {'first name': 'doldoldol', 'last name': 'lee', 'dept': '2', 'address': 'addr22222'},
        {'first name': 'dong', 'last name': 'ja', 'dept': '3', 'address': 'addr33333'},
        {'first name': 'wall', 'last name': 'pong', 'dept': '1', 'address': 'addr44444'}
      ]
    }
  },
  methods: {
    onClickCheckbox (selected) {
      console.log(selected)
    }
  }
}
</script>
