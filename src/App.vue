<template>
  <div id="app">
    <header>
      <h1>Here is a test page for all of the bits</h1>
    </header>

    <section>
      <header>
        <h2>Button</h2>
      </header>

      <hr>

      <vic-button></vic-button>

      <hr>

      <vic-button
        text="Clicky Clicky"></vic-button>

    </section>

    <section>
      <header>
        <h2>Datatable</h2>
      </header>

      <hr>

      <vic-datatable></vic-datatable>

      <hr>

      <vic-datatable 
        :row-data="datatable.rowData"
        :caption="datatable.caption"></vic-datatable>

      <hr>

      <vic-datatable 
        :col-headers="datatable.colHeaders"
        :row-data="datatable.rowData"
        :caption="datatable.caption"></vic-datatable>

      <hr>

      <vic-datatable 
        :col-headers="datatable.colHeaders"
        :row-data="datatable.rowData"
        :caption="datatable.caption"
        :col-spec="datatable.colSpec"></vic-datatable>
    </section>

  </div>
</template>

<script>
import VicButton from './components/Button.vue';
import VicDatatable from './components/Datatable.vue';

export default {
  name: 'app',

  data () { 
    return {
      datatable: {
        caption: 'Ice Cream Feedback',
        colHeaders: ['Flavor', 'Taste', 'Texture', 'Price'],
        colSpec: [
          {
            header: true
          },
          {},
          {},
          {}
        ],
        rowData: [
          ['Chocolate', 4, 3, 2.99],
          ['Vanilla', 5, 4, 3.49],
          ['Oreo Cookie', 3, 5, 4.99],
        ],
        complexRowData: [
          [
            {
              value: 'Chocolate',
              header: true
            },
            {
              value: 4,
            },
            {
              value: 3
            },
            {
              value: 2.99
            }
          ],
        ]
      }
    }
  },

  components: {
    VicButton,
    VicDatatable,
  },
};
</script>

<style lang="sass">
html, body
  font-family: 'Montserrat', sans-serif
  font-size: 18px
</style>
