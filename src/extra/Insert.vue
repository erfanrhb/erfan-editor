<template>
  <div>
    <button class="btn p-0 bg-light" @click="addImage" data-toggle="tooltip" title="" data-original-title="تصویر">
      <v-icon>mdi-image-area</v-icon>
    </button>

    <button class="btn p-0 bg-light" @click="addLink" data-toggle="tooltip" title="" data-original-title="لینک">
      <v-icon>mdi-link</v-icon>
    </button>

    <button class="btn p-0 bg-light" @click="insertHtml" data-toggle="tooltip" title="" data-original-title="لینک">
      <v-icon>mdi-video-plus</v-icon>
    </button>
  </div>
</template>

<script>
export default {
  name: "Insert",
  methods: {
    addImage() {
      this.$emit('command', 'insertImage', prompt('آدرس عکس خود را وارد فرمایید'));
    },
    addLink() {
      this.$emit('command', 'createLink', prompt('لینک موردنظر خود را وارد فرمایید'));
    },
    insertHtml() {
      let editCss = prompt('کد کپی شده از آپارات را وارد کنید.')

      editCss = editCss.replace(/<style>.*<\/style>/g, '');
      editCss = editCss.replace('<iframe', '<iframe style="width:604px;height:270px"');

      this.$emit('command', 'insertHTML',editCss);
    }
  }
}
</script>

<style scoped src="bootstrap/dist/css/bootstrap.css"></style>

<style scoped>

</style>
