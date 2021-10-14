<template>
  <q-card>
    <q-card-section>
      <div class="text-h6">Alert</div>
    </q-card-section>

    <q-card-section class="q-pt-none">
      <p>message{{message}}</p>
      <p>someObj {{someObj}}</p>
      <p>someArray {{someArray}}</p>
      <p>someNumber {{someNumber}}</p>
      <p>someBoolean {{someBoolean}}</p>
    </q-card-section>

    <q-card-actions align="right">
      <q-btn flat label="CLOSE" color="primary" @click="closeDialog" />
    </q-card-actions>
  </q-card>
</template>

<script>
export default {
  name: "DialogCards",
  props:{
    message: {
      type: String,
      default: 'Default title'
    },
    someObj: {
      type: Object,
      default: () => {}
    },
    someArray: {
      type: Array,
      default: () => {}
    },
    someFunction: {
      type: Function,
      default: () => {}
    },
    someNumber: {
      type: Number,
      default: 0
    },
    someBoolean: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    checkFunctionProps () {
      this.someFunction()
    },
    closeDialog () {
      this.$emit('closeModalDialog', false)
      this.$emit('getConsole', 'this message from child component')
    }
  }
}
</script>

<style scoped>

</style>
