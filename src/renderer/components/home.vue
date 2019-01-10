<template>
    <Row>
      <Col span="3">PT-License 激活工具</Col>
      <Col span="3">col-12</Col>
      <Input v-model="value" placeholder="Enter something..." style="width: 300px" />
    </Row>
  <Tabs value="name1">
    <TabPane label="标签一" name="name1">标签一的内容</TabPane>
    <TabPane label="标签二" name="name2">标签二的内容</TabPane>
    <TabPane label="标签三" name="name3">标签三的内容</TabPane>
  </Tabs>
</template>

<script>
  export default {
    name: 'main-page',
    data () {
      return {
        value: 'ssssss'
      }
    },
    methods: {
    }
  }
</script>

<style>


</style>
