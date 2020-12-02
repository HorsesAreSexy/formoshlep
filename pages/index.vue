<template>
  <div>
    <div v-for="(item, key) in selects" :key="key" class="item">
      <div is="Dropdown" v-model="item.mare" :list="mares" class="input">
        Какую поню ты хочешь?
      </div>
      <div
        is="Dropdown"
        v-model="item.action"
        :class="item.mare || 'hidden'"
        :disabled="item.mare === undefined && 'disabled'"
        :list="actions"
        class="input"
      >
        Что ты хочешь с ней делать?
      </div>
      <img :src="(item.mare ? mares[item.mare].vector : 'wt') + '.png'" class="vector">
    </div>
    <div class="add" @click="addMare">
      Добавить кобылочку
    </div>
  </div>
</template>

<script>
import Dropdown from '~/components/Dropdown'
export default {
  components: {
    Dropdown
  },
  data () {
    return {
      mares: [
        {
          name: 'Twilight Sparkle',
          vector: 'ts'
        },
        {
          name: 'Rarity',
          vector: 'rr'
        },
        {
          name: 'Fluttershy',
          vector: 'fl'
        },
        {
          name: 'Applejack',
          vector: 'ap'
        },
        {
          name: 'Rainbow Dash',
          vector: 'rd'
        },
        {
          name: 'Pinkie Pie',
          vector: 'pp'
        },
        {
          name: 'Trixie',
          vector: 'tr'
        },
        {
          name: 'Rara',
          vector: 'ra'
        },
        {
          name: 'Баклажак',
          vector: 'bj'
        }
      ],
      actions: [
        'Обнять',
        'Бупнуть носик',
        'Погладить гривку',
        'Почесать за ушком',
        'Помассировать копытца',
        'Заварить чаёчку *wink wink*'
      ],
      selects: [{}]
    }
  },
  methods: {
    addMare () {
      this.selects.push({})
    }
  }
}
</script>

<style lang="scss">
.hidden{
  opacity: 0;
}
.item{
  margin-bottom: 100px;
  border: 4px solid gray;
  border-radius: 4px;
  box-shadow: 0 0 2px 0 black;
  position: relative;
  padding: 20px;
  .input:not(:first-of-type){
    margin-top: 20px;
  }
  .vector{
    max-height: 300px;
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
  }
}
.add{
  border: 6px solid orange;
  border-radius: 10px;
  padding: 10px 20px;
  font-size: 40px;
  font-weight: bold;
  text-transform: uppercase;
  color: dimgray;
  background: rgba(255, 153, 0, 0.2);
  display: inline-block;
  margin-bottom: 100px;
  cursor: pointer;
}
</style>
