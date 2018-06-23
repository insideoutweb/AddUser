<template>
<div class="overallDivs">  
  <card class="cardSigup text-center">
    <row>
      <column md="8">
        <input type="text" class="form-control mt-4" id="usr" v-model="text" placeholder="Email Address here">
        <!-- <input  class="textbox mt-4" v-model="text" placeholder="Email Address here"> -->
      </column>
      <column md="4">
        <btn id="button" type="button" v-on:click.native="add" class="button btn btn-google-plus w-80" v-bind:class="text">Add</btn>
      </column>
    </row>
  </card>
<div class="mt-3">
  <card>
  <table class="table table-striped table-hover">
    <thead>
      <tr>
        <th style="width: 25px;"></th>
        <th>Email Address</th>
        <th>Create</th>
        <th>Run</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="row in rows">
        <td></td>
        <td>{{row.email}}</td>
        <td><input type="checkbox"></td>
        <td><input type="checkbox"></td>
        <td><btn id="button" type="button" class="button btn btn-google-plus w-80">Save</btn></td>
      </tr>      
    </tbody>
  </table>
  </card>
</div> 
</div>
</template>
<script>
import Btn from '../components/Button';
import Column from '../components/Col';
import Row from '../components/Row';
import Container from '../components/Container';
import Card from '../components/Card';
import CardBody from '../components/CardBody';
export default {
  // el: '#button',
  name: 'JustDeploy',
  components: {
    Btn,
    Column,
    Row,
    Container,
    Card,
    CardBody,
  },
  data(){
    return {
      rows: [],
      text:''
    };
  },
  methods: {
    add(){
      // console.log(this.text);
      this.rows.push({email: this.text});
      this.text="";
    }
  }
};
</script>
<style scoped>
.table {
    margin-left: 73px;
    width: 89%;
    max-width: 100%;
    margin-bottom: 1rem;
    background-color: transparent;
}
.overallDivs{
  margin-left: 50px;
  margin-right: 50px;
}
.form-control{
  margin-left: 50px !important;
  margin-right: 50px !important;
  width:80% !important;
  margin-top:10px;
  margin-bottom:10px;
}
.cardSigup{
  padding: 30px;
}
</style>