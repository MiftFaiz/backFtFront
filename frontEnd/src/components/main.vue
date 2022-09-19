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