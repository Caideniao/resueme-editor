<script>
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
export default  new Vuex.Store({
  state: {
    resume:{
    profile: [{'姓名':'','年龄':'','关于':''}],
    schooles:[{'学校':'','时间':'','学位':''}],
    jobs:[{'公司':'','时间':'','职责':''}],
    skills:[{'技能':'','兴趣':'','其他':''}]}
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
        console.log(state.resume[s])
        console.log(t)
        state.resume[s].splice(t,1)
    }
  }
})
</script>