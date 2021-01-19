<template>
  <div>
    <vxe-button status="primary" @click="test">点击</vxe-button>
    <vxe-button status="primary" @click="testreade">读取文件</vxe-button>
    <vxe-button status="primary" @click="saveFiles">保存HTML文件</vxe-button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: '郭治国test vxe-table 3.X版本'
    }
  },
  methods: {
    test() {
      this.$XModal.message({ message: ' 测试 ', status: 'error' })
    },
    async testreade() {
      const { files } = await this.$XReadFile({ multiple: true })
      this.$XModal.alert(`共：${files.length} 个文件`)
    },
    async saveFiles() {
      this.$XSaveFile({
        filename: '页面',
        type: 'html',
        content: '<html><head></head><body>内容xx</body></html>'
      })
    },
  },
}
</script>
