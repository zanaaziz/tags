<template>
  <div class="jumbotron" style="background-color: #eeeeee;">
    <h1 class="display-4">TAGS</h1>
    <p class="lead">A simple tagging system in Vue.js.</p>
    <hr class="my-4">
    <app-progress :numOfTags="tags.length" :maxNumOfTags="maxNumOfTags"></app-progress>
    <app-new-tag-form @tagAdded="newTag"></app-new-tag-form>
    <hr class="my-4">
    <div class="sm-12 text-center">
      <div class="alert alert-info">Note: To delete a tag, simply click on it.</div>
    </div>
    <app-grid :tags="tags" @tagDeleted="deleteTag"></app-grid>
  </div>
</template>

<script>
import Grid from "./components/Grid.vue";
import NewTag from "./components/NewTag.vue";
import Progress from "./components/Progress.vue";

export default {
  name: 'app',
  data () {
    return {
      tags: [],
      maxNumOfTags: 10
    }
  },
  methods: {
    newTag(tag){
      if(this.tags.length < this.maxNumOfTags){
        this.tags.push(tag);
      }else{
        alert("You have reached the maximum number of tags.");
      }
    },
    deleteTag(index){
      this.tags.splice(index, 1);
    }
  },
  components: {
    appGrid: Grid,
    appNewTagForm: NewTag,
    appProgress: Progress
  }
}
</script>

<style>
  body{
    background-color: #eeeeee;
  }
</style>
