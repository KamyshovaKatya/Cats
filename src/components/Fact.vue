<template>
  <p id="fact">
    О кошках: {{ values.fact }}
  </p>
</template>

<script>
export default {
  props: ['values'],
};
</script>

<style>
#fact {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  flex-wrap: wrap;
  width: 400px;
  padding: 30px;
  background-color: white;
  border-radius: 20px;
  box-shadow: 0px 0px 10px 0px rgba(50, 50, 50, 0.75);
}
</style>