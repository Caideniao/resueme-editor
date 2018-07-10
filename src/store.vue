<script>
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
export default  new Vuex.Store({
  state: {
    resume:{
    profile: [{'姓名':'测试内容','年龄':'测试内容','关于':'测试内容测试内容测试内容测试内容测试内容测试内容测试内容测试内容'}],
    schooles:[{'学校':'测试内容','时间':'测试内容','学位':'测试内容'}],
    jobs:[{'公司':'测试内容','时间':'测试内容','职责':'测试内容'}],
    skills:[{'技能':'测试内容','兴趣':'测试内容','其他':'测试内容'}]},
    path:null
  },
  mutations: {
    setData (state,n) {
      state.count++
    },
    updateData (state, n) {
        let s = n.t
        let t = n.value
        let o = n.title
        let i = n.ind
        state.resume[s][i][o] = t

    },
    updateList (state, n){
        if (n === 'profile'){
            state.resume[n].push({'姓名':'','年龄':'','关于':''})
        } else if (n === 'schooles') {
            state.resume[n].push({'学校':'','时间':'','学位':''})
        } else if (n === 'jobs') {
            state.resume[n].push({'公司':'','时间':'','职责':''})
        } else {
            state.resume[n].push({'技能':'','兴趣':'','其他':''})
        }  
        
    },
    deleteList (state,n){
        let s = n.title
        let t = n.index
        state.resume[s].splice(t,1)
    },
    setPath(state,n){
        state.path = n
    }
  }
})
</script>