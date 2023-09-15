<template>
<div class="container-card text-center" style="margin-top: 10px;">
      <div class="row">
        <div class="d-flex flex-wrap justify-content-between">
          <div v-for="(item, index) in tlAttraction"  class="card" style="width: 18rem;">
            <img class="card-img-top" v-if="item.name" :src="item.img" alt="Card image cap">
            <div class="card-body">
              <h5 class="card-title">{{item.name}}</h5>
              
              <button class="btn btn-primary" @click="addToTable(item.name)">Book</button>
            </div>
      </div>
    </div>
  </div>
</div>

<section>
  <table class="table table-hover table-dark" >
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Cafe Name</th>
          <th scope="col"></th>
          <th scope="col"></th>
        </tr>
      </thead>
      <tbody>
      <tr v-for="(name, index) in tableData" :key="index">
        <th scope="row">{{ index + 1 }}</th>
        <td>{{ name }}</td>
        <td></td>
        <td></td>
      </tr>
    </tbody>
    </table>
  </section>

  <form class="row g-3">
  <div class="col-md-4">
    <label for="validationServer01" class="form-label">Full Name</label>
    <div class="input-group has-validation">
      <input type="text" class="form-control is-invalid" id="validationServer01" aria-describedby="inputGroupPrepend3 validationServer01Feedback" required>
      <div id="validationServer01Feedback" class="invalid-feedback">
        Please choose a username.
      </div>
    </div>
  </div>
  <div class="col-md-4">
    <label for="validationServer01" class="form-label">Phone number</label>
    <div class="input-group has-validation">
      <input type="tel" class="form-control is-invalid" id="validationServer01" aria-describedby="inputGroupPrepend3 validationServer01Feedback" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" placeholder="012-345-6789" required />
>
      <div id="validationServer01Feedback" class="invalid-feedback">
        Please choose a username.
      </div>
    </div>
  </div>
  <div class="col-md-4">
    <label for="validationServer01" class="form-label">Amount (The table)</label>
    <div class="input-group has-validation">
      <input type="number" class="form-control is-invalid" id="validationServer01" aria-describedby="inputGroupPrepend3 validationServer01Feedback" required>
      <div id="validationServer01Feedback" class="invalid-feedback">
        Please choose a username.
      </div>
    </div>
  </div>
  <div class="col-12">
    <button class="btn btn-primary" type="submit">Submit form</button>
  </div>
</form>
</template>

<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from 'vue-router'
import { defineProps } from 'vue';

const travel = ref("");
const money = ref(0);

  //const tlAttraction = ref(['ท่าช้าง', 'GoodViews', 'RiverSide', 'WarmUp', 'ID4'])
const tlAttraction = ref([
    { name:'ท่าช้าง', price:80, size: { s: 80, m: 150, l: 200 }, img: "https://www.awaygpub.com/wp-content/uploads/2021/03/%E0%B8%97%E0%B9%88%E0%B8%B2%E0%B8%8A%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%84%E0%B8%B2%E0%B9%80%E0%B8%9F%E0%B9%88-%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B9%80%E0%B8%AB%E0%B8%A5%E0%B9%89%E0%B8%B2%E0%B8%8A%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%94%E0%B8%B1%E0%B8%87%E0%B9%83%E0%B8%88%E0%B8%81%E0%B8%A5%E0%B8%B2%E0%B8%87%E0%B9%80%E0%B8%A1%E0%B8%B7%E0%B8%AD%E0%B8%87%E0%B9%83%E0%B8%AB%E0%B8%A1%E0%B9%88-awaygpub-3.jpg" }, 
    { name:'GoodViews', price:120, size: { s: 80, m: 150, l: 250 }, img: "https://www.chillnaid.com/wp-content/uploads/2017/08/P8220053-1024x768.jpg" }, 
    { name:'RiverSide', price:150, size: { s: 80, m: 150, l: 300 }, img: "http://www.dooasia.com/wp-content/uploads/2018/05/The-RiverSide-%E0%B9%80%E0%B8%8A%E0%B8%B5%E0%B8%A2%E0%B8%87%E0%B9%83%E0%B8%AB%E0%B8%A1%E0%B9%88-7.jpg" }, 
    { name:'WarmUp', price:100, size: { s: 80, m: 150, l: 500 }, img: "https://pbs.twimg.com/media/EIhrLy9U8AEdpUl?format=jpg&name=large" }, 
    { name:'THAY Nimman', price:90, size: { s: 80, m: 150, l: 700 }, img: "https://scontent.fbkk29-8.fna.fbcdn.net/v/t39.30808-6/275553294_5447999895223902_8749872957228405946_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=49d041&_nc_eui2=AeEtKuerdYNz5dSuF8ZX1MwgX-Daxlw776Zf4NrGXDvvpg2jJFyn78TRGStcpmcaiObMHRkit2XONItgBS-9tFZv&_nc_ohc=fPkZSb_2BZwAX__g6jl&_nc_ht=scontent.fbkk29-8.fna&oh=00_AfD4M2E-zJcCvlnDcTt6REOCWcg129JJw49EOntogr6yDA&oe=65089127" },
    { name:'Lism Cafe', price:90, size: { s: 80, m: 150, l: 700 }, img: "https://img.wongnai.com/p/1920x0/2019/07/14/7e31672612ba4462b77d77cd41ca83e7.jpg" },
    { name:'Beer Lab', price:90, size: { s: 80, m: 150, l: 700 }, img: "https://img.wongnai.com/p/1920x0/2016/08/25/9998216c3b5f4670a016571ed558ab6c.jpg" },
    { name:'TAMMA Cafe', price:90, size: { s: 80, m: 150, l: 700 }, img: "https://scontent.fbkk29-7.fna.fbcdn.net/v/t39.30808-6/275609725_2224948664309812_6792567553159522822_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=5614bc&_nc_eui2=AeE6N7qrwWoByAJT0YeOxjKBUUvIys2tUyBRS8jKza1TIAJHeP1JLfdrczNlflD-yuhREhBk_8mFHJ2nqL66QBT5&_nc_ohc=sOLirVbae6QAX-B2aSc&_nc_ht=scontent.fbkk29-7.fna&oh=00_AfD9YPdF3AfoGJfIvqZ-TNVCFJmv3pLKpVUgevw063XEzw&oe=650990C6" }
  ]); 

const tableData = ref([]); // Create a ref for the table data

const addToTable = (name) => {
  tableData.value.push(name); // Add the selected name to the table data
};

document.body.classList.remove('page-a-body');
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

* {
  margin: 0;
  padding: 0;
}

.container-card .row{
  display: flex;
  justify-content: center;
  align-items: center;
}

section table {
  margin-top: 15px;
}
</style>
