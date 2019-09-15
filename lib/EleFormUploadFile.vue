<template>
  <ele-upload-file
    :class="desc.class"
    :style="desc.style"
    class="ele-form-upload-file"
    v-bind="attrs"
    v-model="newValue"
    v-on="onEvents"
  />
</template>

<script>
import EleUploadFile from 'vue-ele-upload-file'
import formMixin from 'vue-ele-form/lib/mixins/formMixin'
import uploadMixin from 'vue-ele-form/lib/mixins/uploadMixin'

export default {
  name: 'EleFormFile',
  mixins: [ formMixin, uploadMixin ],
  components: {
    EleUploadFile
  }
}
</script>

<style>
.ele-form-upload-file .el-upload__tip {
  line-height: 1.5;
}

.ele-form-upload-file .el-upload-list__item:first-child {
  margin-top: 5px;
}
</style>
