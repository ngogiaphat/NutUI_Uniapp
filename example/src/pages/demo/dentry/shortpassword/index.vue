<script lang="ts">
import { reactive } from 'vue'

export default {
  setup() {
    const state = reactive({
      visible1: false,
      visible2: false,
      visible3: false,
      visible4: false,
      showKeyboard1: false,
      showKeyboard2: false,
      showKeyboard3: false,
      showKeyboard4: false,
      value1: '',
      value2: '',
      value3: '',
      value4: '',
      errorMsg: '',
      length: 6,
      show: false,
      cover: false,
    })
    const methods = {
    /* eslint-disable no-console */
      complete(value: any) {
        console.log(value)
      },
      onTips() {
        state.show = true
        state.cover = false
      },
      close() {},
      cancel() {},
    }

    return {
      state,
      methods,
    }
  },
}
</script>

<template>
  <div class="demo">
    <nut-cell title="基础用法" is-link @click="state.visible1 = true" />
    <nut-short-password
      v-model="state.value1"
      v-model:visible="state.visible1"
      @focus="state.showKeyboard1 = !state.showKeyboard1"
      @close="state.showKeyboard1 = false"
    />
    <nut-number-keyboard v-model="state.value1" v-model:visible="state.showKeyboard1" />

    <nut-cell
      title="自定义密码长度4"
      is-link
      @click="
        state.visible2 = true;
        state.length = 4;
      "
    />
    <nut-short-password
      v-model="state.value2"
      v-model:visible="state.visible2"
      :length="state.length"
      @focus="state.showKeyboard2 = !state.showKeyboard2"
      @close="state.showKeyboard2 = false"
      @complete="methods.complete"
    />
    <nut-number-keyboard v-model="state.value2" v-model:visible="state.showKeyboard2" maxlength="4" />
    <nut-cell
      title="忘记密码提示语事件回调"
      is-link
      @click="
        state.visible3 = true;
        state.length = 6;
        state.errorMsg = '';
      "
    />
    <nut-short-password
      v-model="state.value3"
      v-model:visible="state.visible3"
      @focus="state.showKeyboard3 = !state.showKeyboard3"
      @close="state.showKeyboard3 = false"
      @tips="methods.onTips"
    />
    <nut-number-keyboard v-model="state.value3" v-model:visible="state.showKeyboard3" />

    <nut-cell
      title="错误提示语"
      is-link
      @click="
        state.visible4 = true;
        state.length = 6;
        state.errorMsg = '请输入正确密码';
      "
    />
    <nut-toast v-model:visible="state.show" msg="忘记密码" type="text" :cover="state.cover" />
    <nut-short-password
      v-model="state.value4"
      v-model:visible="state.visible4"
      :error-msg="state.errorMsg"
      @focus="state.showKeyboard4 = !state.showKeyboard4"
      @close="state.showKeyboard4 = false"
      @tips="methods.onTips"
    />
    <nut-number-keyboard v-model="state.value4" v-model:visible="state.showKeyboard4" />
  </div>
</template>

<route lang="json">
{
  "style": {
    "navigationBarTitleText": "ShortPassword"
  }
}
</route>
