<script setup lang="ts">
const text: string = "Hello, World!";

// data
const textRef = ref("ref data");
// data こっちの方がv2のdataに近い？
const dataReactive = reactive({
  form: {
    name: "",
  },
  users: [],
});

// computed
const computed1 = computed(() => text + "computed1");
const computed2 = computed(() => text + "computed2");

// method
const method = (a: string) => {
  return "method" + a;
};

// createdわからん
setTimeout(() => {
  console.log("created");
}, 3000);

// usestate状態管理
const { counter, inc, dec } = useSharedCounter();

// mounted
onMounted(() => {
  console.log(counter.value);
});
</script>

<template>
  <div>
    カウンター: {{ counter }}
    <button @click="inc">+</button>
    <button @click="dec">-</button>
    <div>
      <h1>{{ text }}</h1>
      {{ textRef }} <br />
      {{ dataReactive }} <br />
      {{ computed1 }} <br />
      {{ computed2 }} <br />
      {{ method("です") }}
    </div>
  </div>
</template>
