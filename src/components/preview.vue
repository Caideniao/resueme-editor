<template>
    <div class="preview-container">
        <div class="preview-avatar">
            <div class="avatar-img"><img src="../assets/Pikachu.png" alt="头像" class="avatar-pikachu"></div>
            <p class="avatar-age"><span>{{content.profile[0]['姓名']}}</span> &nbsp; <span >{{content.profile[0]['年龄']}}</span></p>
        </div>
        <div class="information">
            <div class="information-icon">
            <svg class="icon" aria-hidden="true" >
            <use xlink:href="#icon-gerenzhongxin"></use></svg>
            <p>ABOUT ME</p></div>
            <div class="information-me"><p>&nbsp;&nbsp;&nbsp;&nbsp;{{content.profile[0]['关于']}}</p></div>
        </div>
        <div class="education">
             <div class="education-icon">
            <svg class="icon" aria-hidden="true" >
            <use xlink:href="#icon-jiaoyubeijing"></use></svg>
            <p>EDUCATION</p></div>
            <div class="education-list" v-for='item in content.schooles' v-bind:key="item.id">
                <div class="education-container">
                <img src="../assets/school.jpg" alt="">&nbsp;&nbsp;&nbsp;&nbsp;{{item['时间']}}
                <div class="education-content"><span></span><p>{{item['学校']}}&nbsp;&nbsp;{{item['学位']}}</p></div></div>
            </div>   
        </div>
        <div class="jobs">
            <div class="jobs-icon">
            <svg class="icon" aria-hidden="true" >
            <use xlink:href="#icon-10"></use></svg>
            <p>WORK EXPERIENCE</p></div>
            <div class="education-list" v-for='item in content.jobs' v-bind:key="item.id">
                <div class="education-container">
                <img src="../assets/school.jpg" alt="">&nbsp;&nbsp;&nbsp;&nbsp;{{item['时间']}}
                <div class="education-content"><span></span><p>{{item['公司']}}&nbsp;&nbsp;{{item['职责']}}</p></div></div>
            </div>
        </div>
    </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
    computed:{
  ...mapState({
    content: state => state.resume,
  }),
    
}

}
</script>

<style lang="scss" scoped>
 .education-list{
            .education-container{
                img{
                width: 28px;height: 28px;
                margin-left:50px; 
            }
            .education-content{
                margin-left: 64px;
                span{
                    display: inline;
                    border-left: 2px solid;
                    padding: 10px 15px;
                }
                p {
                    display: inline-block;
                }
            }
            }
            
        }
  .information-me{
            min-height: 100px;
           box-shadow: 0px 0px 2px 0px rgba(0,0,0,0.5);
           border-radius: 5px;
           background-color: rgb(202, 223, 233);
           color: rgba(12, 7, 1, 0.623);
            >p{
                margin:0;
                padding: 10px;
            }
        }
 .jobs-icon, .education-icon, .information-icon{
        p {
            display: inline-block;
            vertical-align: top;
            color: lightskyblue;
        }
        .icon{
            width: 35px;height: 35px;
            margin:10px;
        }}
.preview-container{
    margin: 10px 20px;
    overflow: auto;
    .preview-avatar{
        background-color: lightsalmon;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        padding-top: 20px;
        padding-bottom: 10px;
        .avatar-age{
            font-size:24px;
            margin: 10px;
        }
        > .avatar-img{
            background-color: lightcyan;
            width: 80px;
            height:80px;
            border-radius: 40px;
         .avatar-pikachu{
            width: 80px;
            height:80px;
            border-radius: 40px;
        }}
    }
    .education{
     
    }
}

</style>
