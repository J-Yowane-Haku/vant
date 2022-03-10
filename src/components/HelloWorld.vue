<script setup>
import { useParent } from "@vant/use"
import { FORM_KEY } from "vant/es/utils/constant"

defineProps({
  msg: {
    type: String,
    required: true,
  },
  readonly: {
    type: Boolean,
    default: false,
  },
})

const { parent: form } = useParent(FORM_KEY)
</script>

<template>
  <div class="greetings">
    <van-field label="xxx" :readonly="readonly || form.props.readonly"></van-field>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
