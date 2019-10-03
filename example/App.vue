<template>
  <el-card
    header="ele-form-upload-file 演示"
    shadow="never"
    style="max-width: 1250px;margin: 20px auto;"
  >
    <ele-form
      :form-data="formData"
      :form-desc="formDesc"
      :request-fn="handleRequest"
      @request-success="handleSuccess"
    />
  </el-card>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      formData: {
        files: []
      },
      formDesc: {
        files: {
          label: '附件',
          type: 'upload-file',
          attrs: {
            action: 'https://jsonplaceholder.typicode.com/posts',
            responseFn (response, file) {
              return {
                name: file.name,
                url: URL.createObjectURL(file.raw),
                size: file.size
              }
            }
          }
        }
      }
    }
  },
  methods: {
    handleRequest (data) {
      console.log(data)
      return Promise.resolve()
    },
    handleSuccess () {
      this.$message.success('提交成功')
    }
  },
  mounted () {}
}
</script>

<style>
body {
  background-color: #f0f2f5;
}
</style>
