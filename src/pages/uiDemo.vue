<template>
  <div class="container">
    <div class="content">
      <div class="variable">
        <div class="btn-container"> 
          <button class="btn" @click="addItem">add item</button>
          <button class="btn" @click="reduceItem">reduce item</button>
        </div>
        <ul>
          <li v-for="item in items" :key="item.id">
            <div class="item">{{item.name}}</div>
          </li>
        </ul>
      </div>
      <div class="item-input">
        <input placeholder="填写备注，限制20个字符" maxlength="20" class="comment" v-model.lazy="comment" @change="getComment"/>
      </div>
    </div>
  </div>  
</template>

<script>
export default {
  data() {
    return {
      items: [
        { name: '测试item' },
        { name: '测试item' },
        { name: '测试item' },
        { name: '测试item' },
        { name: '测试item' }
      ]
    }
  },
  methods: {
    addItem() {
      this.items.push({ name: '添加的测试item' })
    },
    reduceItem() {
      this.items.splice(this.items.length - 1, 1)
      console.log('length: ', this.items.length)
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
}
.content{
  width: 100%;
  height: 100vh;
  overflow: scroll;
}
.variable {
  width: 100%;
  min-height: 86%;
  flex-direction: column;
}
.btn-container {
  width: 100%;
  display: flex;
  margin-bottom: 40rpx;
}
.btn {
  display: flex;
  flex: 1;
  margin: 20rpx 40rpx;
}
.item {
  width: 100%;
  height: 120rpx;
  line-height: 120rpx;
  text-align: center;
  border-bottom: 1px solid #e0e0e0;
}
.item-input {
  width: 100%;
  display: flex;
  justify-content: center;
}

.comment {
  width: 88%;
  font-size: 9pt;
  padding: 10rpx 20rpx;
  border: 1px solid #e0e0e0;
  border-radius: 4pt;
  margin-top: 16rpx;
  margin-bottom: 10rpx;
}
</style>


