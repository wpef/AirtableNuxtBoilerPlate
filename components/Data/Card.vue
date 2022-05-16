<template>
  <div
    class="h-full border-2 border-gray-200 border-opacity-60 rounded-lg overflow-hidden"
  >
      <h1 class="title-font text-lg font-medium text-gray-900 mb-3">
        <!-- Edit fields here-->
        {{ data.Eval }}
        <utilsLearnMore :label="'single'" :link="link" />
      </h1>

  </div>
</template>
<script>
export default {
  props: ['myData'],

  data() {
    console.log(this.myData)
    return {
      data: this.myData.fields,
      link: '/' + this.myData.id,
    }
  },
}
</script>
