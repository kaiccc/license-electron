<template>
    <div style="margin: 20px; text-align: center">
        <Row>
            <Col span="24">
                <h2>PowerTool - 授权工具</h2>
            </Col>
        </Row>
        <Row style="margin-top: 20px">
            <Col span="6" ><h3 >机器码：</h3></Col>
            <Col span="18">
                <Input v-model="hostCode" placeholder="请输入机器码" />
                <!--//size="small"-->
            </Col>
        </Row>

        <Row style="margin-top: 20px">
            <Col span="6">
                <h3>激活码：</h3>
            </Col>
            <Col span="18" style="text-align: left">
                <Input v-model="license" placeholder="" />
            </Col>
        </Row>
        <Divider/>
        <Row style="margin-top: 10px">
            <Col span="6" offset="9">
                <Button type="success" @click="generate">授权</Button>
            </Col>
        </Row>
    </div>
</template>

<script>
  import md5 from 'js-md5'
  export default {
    name: 'main-page',
    data () {
      return {
        hostCode: '',
        license: ''
      }
    },
    methods: {
      generate () {
        if (this.hostCode === '') {
          this.license = '请输入机器码'
          return
        }
        const hostCode = this.hostCode.trim().replace(/-/g, '').toUpperCase()
        const head = hostCode.substring(0, 4)
        const end = hostCode.substring(hostCode.length - 8)
        const md5Str = md5(end + head).substring(0, 16).toUpperCase()
        this.license = md5Str.substring(0, 4) + '-' + md5Str.substring(4, 8) + '-' + md5Str.substring(md5Str.length - 8)
      }
    }
  }
</script>

<style>


</style>
