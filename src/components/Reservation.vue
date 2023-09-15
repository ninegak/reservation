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
    { name:'ท่าช้าง', price:80, size: { s: 80, m: 150, l: 200 }, img: "src/assets/tahchang.jpg" }, 
    { name:'GoodViews', price:120, size: { s: 80, m: 150, l: 250 }, img: "src/assets/goodviews.jpg" }, 
    { name:'RiverSide', price:150, size: { s: 80, m: 150, l: 300 }, img: "src/assets/riverside.jpg" }, 
    { name:'WarmUp', price:100, size: { s: 80, m: 150, l: 500 }, img: "src/assets/warmup.jpg" }, 
    { name:'THAY Nimman', price:90, size: { s: 80, m: 150, l: 700 }, img: "src/assets/thaynimman.jpg" },
    { name:'Lism Cafe', price:90, size: { s: 80, m: 150, l: 700 }, img: "src/assets/lism.jpg" },
    { name:'Beer Lab', price:90, size: { s: 80, m: 150, l: 700 }, img: "src/assets/beerlab.jpg" },
    { name:'TAMMA Cafe', price:90, size: { s: 80, m: 150, l: 700 }, img: "src/assets/tamma.jpg" }
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
