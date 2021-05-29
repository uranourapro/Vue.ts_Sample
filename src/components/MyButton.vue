<template>
  <button @click="onClick">SampleButton</button>
</template>

<script lang="ts">
import { Component, Prop, Emit, Vue } from "vue-property-decorator";

@Component
export default class MyButton extends Vue {
  // ?はnullを許容するもの
  @Prop()
  public greet?: string;

  // イベントとみなされる
  @Emit()
  public click(): number {
    return 0;
  }

  // ボタンを押すとgreetをアラートで表示
  public onClick() {
    alert(this.greet);
    this.click();
  }
}
</script>