<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 col-md-offset-3">
        <button @click="selectedComponent= 'appMemory' " >appMemory</button>
        <button @click="selectedComponent= 'appAuthor' ">appAuthor</button>
        <button @click="selectedComponent= 'appNewMemory' ">appNewMemory</button>
        <p>{{selectedComponent}}</p>
        <keep-alive>
        <component :is="selectedComponent" >
          <h1 slot="heading" >Başlık</h1>
          <p slot="content" >Bu çok güzel bir anıdır...</p>
        </component>
        </keep-alive>
        <!--<app-memory>
          <h1 slot="heading" >Başlık</h1>
          <p slot="content" >Bu çok güzel bir anıdır...</p>
        </app-memory> -->
      </div>
    </div>
  </div>
</template>

<script>
  import Memory from "./components/Memory";
  import Author from "./components/Author";
  import NewMemory from "./components/NewMemory";

  export default {
    data : function (){
      return {
        selectedComponent : "appMemory"
      }
    },
    components : {
      appMemory : Memory,
      appAuthor : Author,
      appNewMemory : NewMemory
    }
  }
</script>
