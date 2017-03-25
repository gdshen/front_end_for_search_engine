<template>
  <div class="hello">
  
    <el-row>
      <el-col :span="16">
        <div>
          <el-input placeholder="Search"></el-input>
        </div>
      </el-col>
      <el-col :span="8">
        <div>
          <el-button @click="say('hello')">Search</el-button>
        </div>
      </el-col>
    </el-row>
  
    <ul id="result-lists">
      <!--<li v-for="item in items">-->
      <li v-for="item in items">
        <a :href="item.url">{{item.text}}</a>
        <p> {{item.detail}} </p>
      </li>
    </ul>
  
    <div class="block">
      <el-pagination layout="prev, pager, next"
                     @size-change="handleSizeChange"
                     @current-change="handleCurrentChange"
                     :total="items.length">
      </el-pagination>
    </div>
  
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      items: [
        { url: 'http://example.com', text: 'This is a text1', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text2', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text3', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text4', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text5', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text6', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text7', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text8', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text9', detail: 'this is a detail description' },
        { url: 'http://example.com', text: 'This is a text10', detail: 'this is a detail description' }
      ]
    }
  },

  methods: {
    handleSizeChange (val) {
      // console.log(`${val} items per page`)

    },
    handleCurrentChange (val) {
      // update data
      this.currentPage = val
      console.log(`current page: ${val}`)
    },
    say (message) {
      alert(message)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
