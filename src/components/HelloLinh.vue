<template>
  <div>
    <h1>
        My new vue file
    </h1>
    <h2> {{msg_time}} </h2>
  </div>
</template>

<script>
export default {
props: {
    msg_time: String
  },
}
</script>

<style>

</style>