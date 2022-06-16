<template>
<div>
<div class="container">
   <div class="menu">
      <router-link class="menu__item" to="/MyProfileScreen">Мой профиль</router-link>
      <div class= "menu__item menu__item_checked" >Мои статьи</div>
      <router-link class="menu__item"  to="/EditProfileScreen">Редактировать профиль</router-link>
      <a href="#openModal" class="menu__item">Выйти из профиля</a>
    </div>
<div class="articles">
   <div>
      <input @click="visiblemessage =! visiblemessage" type="checkbox" class="checkbox">
      <label  class="message" v-for="item in items" :key="item.message">
         {{item.message}}
      </label>
      <div v-if=" visiblemessage" class="container">
         <a>Статья не цитируется</a>
      </div>
   </div>
    <div>
   <input @click="visiblemessage1 =! visiblemessage1" type="checkbox" class="checkbox">
      <label  class="message" v-for="item in items" :key="item.message1">
         {{item.message1}}
      </label>
      <div v-if=" visiblemessage1" class="container">
         <a>Статья не цитируется</a>
      </div>
      </div>
       <div>
   <input @click="visiblemessage2 =! visiblemessage2" type="checkbox" class="checkbox">
      <label  class="message" v-for="item in items" :key="item.message2">
         {{item.message2}}
      </label>
      <div v-if="visiblemessage2" class="container">
         <a>Статья "АНАЛИТИЧЕСКИЙ ОБЗОР СОВРЕМЕННЫХ ИНФОРМАИОННЫХ ТЕХНОЛОГИЙ В ОБЛАСТИ СБОРА
          <p>  ОБРАБОТКИ И АНАЛИЗА ДАННЫХ, ПРИМИНЯЕМЫХ ДЛЯ МОНИТОРИНГА ЗАГРЯЗНЕНИЙ АТМОСФЕРНОГО ВОЗДУХА"</p></a>
            <p> Цитиретуся в:</p>
            <p> Головина Е.Ю. , Волкова О.Г.</p>
            <p> МОДЕРНИЗАЦИЯ ПРОЦЕССА "КОНТРОЛЬ ЭКОЛОГИЧЕСКОЙ ОБСТАНОВКИ" НА ПРЕДПРИЯТИИ</p>
      </div>
      </div>
       <div>
   <input @click="visiblemessage3 =! visiblemessage3" type="checkbox" class="checkbox">
      <label  class="message" v-for="item in items" :key="item.message3">
         {{item.message3}}
      </label>
      <div v-if=" visiblemessage3" class="container">
         <a>Статья не цитируется</a>
      </div>
      </div>
</div>
      <button class="profile__button" @click="coauthor">Найти соавторов</button>
</div>

<a name="graf" v-if="iscoauthor" class="graf">
      <Graf />
</a>
</div>
</template>

<script>
import Graf from './Graf.vue'
//import axios from 'axios'
export default {
  name: 'MyArticles',
  el:'#example-1',
  data(){
   return{
   items: [
      {message: 'О популяризации наукоемких программных разработок'},
      {message1: 'Применение нестанционарных сетей в задачах'},
      {message2: 'Аналитический обзор современных информаионных технологий...'},
      {message3: 'Беспроводные сенсорные сети, оснащенные средствами получения'}
   ],
    article: {
        id:"",
        coauthor: "",
        titleArticles: "",
        doi: "",
        content: "",
        keywords: "",
        biblecalReference: "",
        file: ""
      },
      visiblemessage: false,
      visiblemessage1: false,
      visiblemessage2: false,
      visiblemessage3: false,
      iscoauthor: false
  }},
  components: {
    Graf
  },
  methods: {
   coauthor(){
      this.iscoauthor=true
   },
}}
</script>
<style lang="less" scoped>
@import '../utils/const.less';
@import '../utils/mixins.less';
.checkbox{
      border: none;
      outline: none;
      background-color: @utility-border-input;
}
.articles{
   display: flex;
   flex-direction: column;
   width: 100%;
   padding: 30px 30px 30px 0;
    margin-left: 10%;
}
.menu{
     width: 200px;
    margin-left: 100px;
    height: 100%;
    display: flex;
    margin-top: 30px;
    background-color: @dark-text-secondary;
    flex-direction: column;
    &__item {
      border: 1px solid @utility-border;
      padding: 8px 8px 14px;
      background-color: rgba(1, 68, 97,0.7);
      color: @utility-white;
      text-decoration: none;
      cursor:pointer;
      &:hover {
        background-color: rgba(1, 68, 97);
      box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1), 0px 4px 20px rgba(0, 0, 0, 0.1);
      } 
      &_checked {
      background-color: rgba(1, 68, 97);
      box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1), 0px 4px 20px rgba(0, 0, 0, 0.1);
    }
    }
}
.container{
   background-color: @utility-border;
}
.profile__button{
   display: flex;
   flex-direction: column;
     text-align: center;
      border: none;
      outline: none;
      .nice-shadow();
      margin-top:10px;
        padding: 5px 5px 5px 5px;
      border-radius: 10px;
      background-color: rgba(1, 68, 97,0.8);
      color: @utility-white;
}

</style>
