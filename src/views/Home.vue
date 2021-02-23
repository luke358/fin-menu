<template>
  <el-menu>
   <child-menu :dataList="listData"></child-menu>
 </el-menu>
</template>
 
<script>
import childMenu from '../components/Menu.vue'
export default {
  components:{
    childMenu
  },
  data(){
    return {
      listData :[
        {
          name: '钠管设备',
          id: "1",
          level: 1,
          child: [
            {
              name: '系统默认组',
              id: "2",
              flag: true
            },
            {
              name: '设备一组',
              id: "3",
              child: [
                {
                  name: '一组A小组',
                  id: "4",
                  child: [
                    {
                      name: '一组A小组的成员1',
                      id: "5"
                    },
                    {
                      name: '一组A小组的成员2',
                      id: "6",
                      child: [
                        {
                          name: '一组A小组的成员何总',
                          id: "7"
                        },
                        {
                          name: '一组A小组的成员曾',
                          id: "8"
                        },
                        {
                          name: '一组A小组的成员飘总',
                          id: "9"
                        }
                      ]
                    }
                  ]
                },
                {
                  name: '一组B小组',
                  id: "10"
                }
              ]
            },
            {
              name: '设备二组',
              id: "11"
            }
          ]
        }
      ]

    }
  }
}
</script>