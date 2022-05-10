<template>
  <div class="inputs" v-for="item in inputs" :key="item.name">
    <input
      :placeholder="item.holder"
      :value="item.value"
      @input="item.value = $event.target.value"
    />
    <button @click="deleteInput(item)">Удалить</button>
  </div>
  <button @click="addInput">Добавить</button>
  asdasd
</template>

<script>
export default {
  name: "MyPage",
  data() {
    return {
      inputs: [
        { name: "input1", id: 0, holder: "something", value: "Щукинская" },
        { name: "input2", id: 1, holder: "something2" },
      ],
      inputsNum: "",
    };
  },
  methods: {
    addInput() {
      this.inputsNum = this.inputs.length + 1;
      this.inputs.push({
        name: `input${this.inputsNum}`,
        holder: `something${this.inputsNum}`,
        id: `${this.inputsNum - 1}`,
        value: "",
      });
    },
    deleteInput(item) {
      this.inputs.splice(item.id, 1);
    },
  },
};
</script>

<style>
</style>