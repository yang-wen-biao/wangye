<template>
  <div>
    <div class="title">课程介绍</div>
    <div style="height: 4px; background-color: #7591f3" >
    </div>
    <div style="height: 100px">
      <p>{{msg}}</p>
    </div>
    <el-footer style="height: 1px;background-color: #7591f3" >
    </el-footer>
  </div>
</template>

<script>
export default {
  name: "gonggao",
  data() {
    return {
      msg:'',
    }
  },
  methods:{
  },
  created() {
    this.$axios.get("/data/1")
        .then((res)=>{
          this.msg=res.data.data;
        })
        .catch(error => {
          this.$message({
            type: 'error',
            message: "查询失败，原因是"+error.data.message
          });
        });
  }
}
</script>

<style scoped>
</style>