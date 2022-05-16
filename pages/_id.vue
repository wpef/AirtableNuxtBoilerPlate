<template>
<div>
  <h1>{{data.id}}</h1>
  <utilsLearnMore :label="'back'" :link="'/'" />
</div>
</template>

<script>
const base = require('airtable').base(process.env.BASE_ID);

export default {
  name: 'Single',

  data() {
    return {
      data: [],
    }
  },

  async fetch() {
    var _this = this

    base(process.env.MAINTABLE_ID).find(_this.$route.params.id, function(err, record) {
        if (err) { console.error(err); return; }
        console.log('Retrieved', record.id);
        _this.data = record.fields;
        _this.data.id = record.id;
    })
  },
  fetchOnServer: false,

  methods: {
  },
}
</script>
