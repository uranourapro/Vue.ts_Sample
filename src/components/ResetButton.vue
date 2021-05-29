<template>
  <button @click="onClick">Reset</button>
</template>

<script lang="ts">
import { Component, Vue, Prop, Emit } from "vue-property-decorator";

@Component
export default class ResetButton extends Vue {
  @Prop({ required: true })
  public initialValue!: string;

  

  @Emit()
  public input(value: string) {
    return value;
  }

  public onClick() {
    this.input(this.initialValue);
  }
}
</script>