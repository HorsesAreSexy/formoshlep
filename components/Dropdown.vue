<template>
  <select :value="value" :class="value || 'question'" @input="$emit('input', $event.target.value)">
    <option disabled :value="undefined">
      <slot />
    </option>
    <option v-for="(item, key) in list" :key="key" :value="key">
      {{ item.name || item }}
    </option>
  </select>
</template>

<script>
export default {
  name: 'Dropdown',
  props: [
    'list',
    'value'
  ]
}
</script>

<style lang="scss">
select{
  width: 500px;
  border: 2px solid gray;
  border-radius: 2px;
  padding: 10px;
  font-size: 30px;
  font-weight: bold;
  display: block;
  &.question{
    color: dimgray;
  }
  option{
    color: black;
  }
}
</style>
