<template>
  <div>
    <p>Wassup Damian</p>
    <button class="btn btn-secondary">Click</button>


    <table class="table table-striped mt-4">
      <thead>
        <tr>
          <th scope="col">UserId</th>
          <th scope="col">Id</th>
          <th scope="col">Title</th>
          <th scope="col">Body</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="post in posts" :key="post.id">
          <td>{{post.userId}}</td>
          <td>{{post.id}}</td>
          <td>{{post.title}}</td>
          <td>{{post.body}}</td>
        </tr>
      </tbody>
    </table>

  </div>
</template>

<script>
  import axios from 'axios'

  export default{
    name: 'PostsExample',
    data(){
      return {
        // posts: [
        //   {id:1,title:'Damian Post 1',body:'ngkusnfkdsnkfdns'},
        //   {id:2,title:'Damian Post 2',body:'ngkusnfkdsnkfdns'},
        //   {id:3,title:'Damian Post 3',body:'ngkusnfkdsnkfdns'},
        //   {id:4,title:'Damian Post 4',body:'ngkusnfkdsnkfdns'},
        //   {id:5,title:'Damian Post 5',body:'ngkusnfkdsnkfdns'},
        // ],
        posts: []
      }
    },
    created(){
      axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(posts =>{
          this.posts = posts.data
        })
    }
  }

</script>

<style>

</style>
