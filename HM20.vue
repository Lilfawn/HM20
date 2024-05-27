<template>
  <div>
    <div class="startwrd">
      <h1>Flex</h1>
    </div>

    <div>
      <h3>justify-content</h3>
      <div class="b-group">

        <button @click="setJustifyContent('flex-start')">start</button>
        <button @click="setJustifyContent('center')">center</button>
        <button @click="setJustifyContent('space-between')">space-between</button>
        <button @click="setJustifyContent('space-around')">space-around</button>
      </div>
    </div>

    <div>
      <h3>align-items</h3>
      <div class="b-group">
        <button @click="setAlignItems('stretch')">stretch</button>
        <button @click="setAlignItems('center')">center</button>
        <button @click="setAlignItems('flex-start')">start</button>
        <button @click="setAlignItems('flex-end')">end</button>
      </div>
    </div>

    <div>
      <button @click="toggleCode">{{ showCode ? 'Hide code' : 'Show code' }}</button>
      <div v-if="showCode">
                <pre>
<code>
.flex-box {
    display: flex;
    justify-content: {{ justifyContent }};
    align-items: {{ alignItems }};
    width: 600px;
    height: 300px;
    border: 1px solid #000000;
}
</code>
                </pre>
      </div>
    </div>

    <div class="flex-box" :style="flexBoxStyle">
      <div class="flex-item"></div>
      <div class="flex-item"></div>
      <div class="flex-item"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      justifyContent: 'flex-start',
      alignItems: 'stretch',
      showCode: false,
    };
  },
  computed: {
    flexBoxStyle() {
      return {
        display: 'flex',
        justifyContent: this.justifyContent,
        alignItems: this.alignItems,
        width: '600px',
        height: '300px',

      };
    },
  },
  methods: {
    setJustifyContent(value) {
      this.justifyContent = value;
    },
    setAlignItems(value) {
      this.alignItems = value;
    },
    toggleCode() {
      this.showCode = !this.showCode;
    },
  },
};
</script>

<style scoped>
.flex-box {
  display: flex;
  width: 600px;
  height: 300px;

}

.flex-item {
  width: 100px;
  height: 50px;
  background-color: orange;
}
.b-group button{
  margin: 5px;
}
.startwrd{
  color: orange;

}
</style>