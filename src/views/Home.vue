<template>
  <div>
  <!-- <a-button class="editable-add-btn" @click="handleAdd">Add</a-button> -->
  <Header></Header>
  <a-table :columns="columns" :dataSource="data" bordered>
    <!-- <template slot="name" >
      {{text}}<a-button type="primary">ALL</a-button>
    </template>
    <template slot="title" >
      菜鸟驿站
    </template>
    <template>
    <div>
    <a-button type="primary">ALL</a-button>
    <a-button>已预约</a-button>
    <a-button type="primary">已取件</a-button>
    <a-button type="primary">未预约</a-button>
    <a-icon type="plus-circle" @click="addItems"/>
    </div>
    </template> -->
    
   
  </a-table>
  </div>
</template>
<script>
import Header from "@/components/Header.vue"

const columns = [{
  title: '运单号',
  dataIndex: 'billCount',
  scopedSlots: { customRender: 'billCount' }
}, {
  title: '收件人',
  className: 'column-money',
  dataIndex: 'name'
}, {
  title: '电话',
  dataIndex: 'phone'
}, {
  title: '状态',
  dataIndex: 'state'
}, {
  title: '预约时间',
  dataIndex: 'happentime'
}, {
  title: ' ',
  dataIndex: 'confirmGoods'
}
];


export default {
  data () {
   return{
      //data,
      columns
    }
  },
  method: {

  },
  components:{
    Header
    
  }
}
</script>
<style>
 .editable-add-btn {
  margin-bottom: 8px;
}
</style>

