<template>
  <div>
    <el-container>
      <el-header style="height: auto">自然语言处理</el-header>
      <el-main>
        <div style="width: 960px; margin: auto; margin-top: 10%; margin-bottom: 10%">
          <el-row>
            <el-col :span="24">
              <div class="grid-content bg-purple-dark"><span style="font-family: 微软雅黑">在线答疑系统</span></div>
            </el-col>
          </el-row>
          <el-row style="width: 780px; margin: 0px 90px">
            <el-col :span="8" style="width: 90px">
              <el-select v-model="value" placeholder="请选择" style="width: 90px">
                <el-option
                  v-for="item in options"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
              </el-select>
            </el-col>
            <el-col :span="8" style="width: 600px">
              <el-input v-model="input" placeholder="请输入问题"></el-input>
            </el-col>
            <el-col :span="8" style="width: 90px">
              <el-button type="primary" icon="el-icon-search">搜索</el-button>
            </el-col>
          </el-row>
          <el-row style="width: 780px; margin: 0px 90px">
          </el-row>
        </div>
      </el-main>
      <el-footer><span style="text-color: #808080">Copyright &copy; 2018  韩大乐</span></el-footer>
    </el-container>
  </div>
</template>
<script>
export default {
  data () {
    return {
      options: [{
        value: '选项1',
        label: '黄金糕'
      }, {
        value: '选项2',
        label: '双皮奶'
      }, {
        value: '选项3',
        label: '蚵仔煎'
      }, {
        value: '选项4',
        label: '龙须面'
      }, {
        value: '选项5',
        label: '北京烤鸭'
      }],
      value: ''
    }
  }
}
</script>
<style>
  .el-header {
    background-color: #495060;
    color: #fff;
    text-align: center;
    padding: 10px;
    font-size: 1.8em;
    font-family: "微软雅黑";
  }

  .el-footer {
    width: 100%;
    background-color: hsla(0, 0%, 93%, .6);
    color: #333;
    text-align: center;
    line-height: 60px;
    font-size: 12px;
  }

  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }

  .el-main {
    /*background-color: #E9EEF3;*/
    color: #333;
    text-align: center;
    /*line-height: 160px;*/
  }
  body > .el-container {
    margin-bottom: 40px;
  }

  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }

  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
