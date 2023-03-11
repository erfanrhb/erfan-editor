<template>
    <div>
        <button class="btn p-0 bg-light" @click="addImage" data-toggle="tooltip" title="" data-original-title="تصویر">
          <v-icon>mdi-multimedia</v-icon>
        </button>

        <button class="btn p-0 bg-light" @click="addLink" data-toggle="tooltip" title="" data-original-title="لینک">
          <v-icon>mdi-link</v-icon>
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
        }
    }
}
</script>

<style scoped src="bootstrap/dist/css/bootstrap.css"></style>

<style scoped>

</style>
