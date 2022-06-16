<style ></style>
<template>
  <div id="app">
    <d3-network
      :net-nodes="nodes"
      :net-links="links"
      :options="options"
       :configs="configs"
    ></d3-network>
<div class="text">
  <a>Соавторы:
   <li>Кратов С.В.</li> 
   <li> Матерухин А.В.</li>
   <li> Шварцкоп Н.С.</li>
  </a>
  <a>Вы являетесь соавтором для:
    <li>Шахов В.В. </li>
   <li> Мигов Д.А.</li> 
  </a>
</div>
    
  </div>
</template>

<script>
import D3Network from "vue-d3-network";

export default {
  name:'Graf',
  components: {
    D3Network,
  },
  data() {
    return {
      nodes: [
        { id: 1, name: "Соколова А.Д.",_size:42, _color: 'rgba(1, 68, 97)' },
        { id: 2, name: "Шахов В.В",_size:42, _color:'rgba(49, 141, 212)'},
        { id: 3, name: "Таранхова О.Ю.",_size:42,_color: "blue"},
        { id: 4,name: "Мигов Д.А",_size:42,_color:'rgba(49, 141, 212)'},
        { id: 5 , name: "Щварцкоп Н.С.",_size:42},
        { id: 6, name: "Кратов С.В.",_size:42},
        { id: 7, name: "Матерухин А.В.",_size:42},
      ],
      links: [
        { sid: 1, tid: 2,type: "resolved"},
        { sid: 1, tid: 4},
        { sid: 3, tid: 2 },
        { sid: 6, tid: 1 },
        { sid: 5, tid: 1 },
        { sid: 7, tid: 1 },
        
      ],
      options: {
        force: 3000,
        nodeSize: 15,
        nodeLabels: true,
        linkWidth: 2,
      },
      configs: ''
      
}}
}
</script>
<style src="vue-d3-network/dist/vue-d3-network.css" >
@import '../utils/const.less';
@import '../utils/mixins.less';
.net_nodes{
  size: 100px,
}
.text{
  border: none;
      outline: none;
  color:#ECEDEE;
}
</style>