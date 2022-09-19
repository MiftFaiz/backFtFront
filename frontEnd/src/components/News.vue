<!-- <template>
  <h1>Hai</h1>
  <EmployeeListvue />
</template>

<script>
import EmployeeListvue from "./components/EmployeeList.vue";
export default {
  name: "App",
  components: {
    EmployeeListvue,
  },
};
</script> -->


<template>

<nav class="navbar navbar-expand-lg bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown
          </a>
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider"></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled">Disabled</a>
        </li>
      </ul>
      <form class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <button class="btn btn-outline-success" type="submit">Search</button>
      </form>
    </div>
  </div>
</nav>

<div v-for="item in list" :key="item" class="" style="width: 18rem">
<div class="card" style="width: 18rem;">
  <img v-bind:src="`${item.urlToImage}`" class="card-img-top" >
  <div class="card-body">
    <h5 class="card-title">{{ item.title }}</h5>
    <p class="card-text">{{item.content}}</p>
    <a :href="item.url" class="btn btn-info">Itulaah Bisaa~~~</a>
  </div>
</div>
</div>

    
      <!-- <img v-bind:src="`${item.urlToImage}`" />
      <div class="">
        <h5 class="">{{ item.title }}</h5>
        <p class="">
          {{item.content}}
        </p>
        <a href="#" class="">Go somewhere</a>
      </div>
    </div> -->
  
    <!-- <ul>
      <li v-for="item in list" :key="item">
        {{ item.author }} {{ item.title }}
        <img v-bind:src="`${item.urlToImage}`" />
      </li>
    </ul> -->
  </template>
  
  <script>
  
  import axios from "axios";
  
  export default {
    name: "News",
    data() {
      return {
        list: [],
      };
    },
    async mounted() {
      let list = await axios.get(
        "https://newsapi.org/v2/top-headlines?country=us&apiKey=52c5f0d990df44308341bd89c86f1115"
      );
      console.warn("data :", list.data.articles);
      this.list = list.data.articles;
    },
  };
  </script>