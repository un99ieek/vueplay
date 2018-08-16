<template>
  <div>
    <h1>Tabletop</h1>
    <v-table :items="items" :fields="fields">
    <template slot="show_details" slot-scope="row">
      <!-- we use @click.stop here to prevent emitting of a 'row-clicked' event  -->
      <button @click.stop="row.toggleDetails">
       {{ row.detailsShowing ? 'Hide' : 'Show'}} Details
      </button>
      <!-- In some circumstances you may need to use @click.native.stop instead -->
      <!-- As `row.showDetails` is one-way, we call the toggleDetails function on @change -->
      <input type="checkbox" @click.native.stop @change="row.toggleDetails" v-model="row.detailsShowing"/>
        Details via check
    </template>
    <template slot="row-details" slot-scope="row">
      <div>
        <div>
          <div><b>Age:</b></div>
          <div>{{ row.item.age }}</div>
        </div>
        <div>
          <div><b>Is Active:</b></div>
          <div>{{ row.item.isActive }}</div>
        </div>
        <button @click="row.toggleDetails">Hide Details</button>
      </div>
    </template>
  </v-table>
  </div>
</template>
<script>
import vTable from '../bsComponents/table'

export default {
  components: {vTable},
  name: 'tabletop',
  data () {
    return {
      fields: [ 'first_name', 'last_name', 'show_details' ],
      items: [
        { isActive: true, age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
        { isActive: false, age: 21, first_name: 'Larsen', last_name: 'Shaw' },
        { isActive: false, age: 89, first_name: 'Geneva', last_name: 'Wilson', _showDetails: false },
        { isActive: true, age: 38, first_name: 'Jami', last_name: 'Carney' }
      ]
    }
  },
  methods: {
    styleRow (item) {
      if (!item) {
        return
      }
      return { 'tr-start-with-l': item.name.first.charAt(0) === 'L', 'tr-last-name-macdonald': item.name.last === 'Macdonald' }
    }
  }
}
</script>
<style>
</style>
