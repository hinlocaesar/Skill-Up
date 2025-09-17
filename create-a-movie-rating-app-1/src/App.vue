<script setup>
import { items } from "./movies.json";
import {reactive} from 'vue'
/*
 This is an Icon that you can use to represent the stars if you like
 otherwise you could just use a simple ⭐️ emoji, or * character.
*/
// import { StarIcon } from "@heroicons/vue/24/solid";
const movies = reactive(items);
</script>

<template>
  <!-- This is where your template goes	-->
  <div class="card_container">
    <div v-for="movie in movies" key="movie.id">
      <div class="movie-card">
        <div class="movie-image">
          <img v-bind:src="movie.image"/>
        </div>
        <div class="movie-details">
          <div class="movie-details-title">
            <div>{{ movie.name }}</div>
          </div>
          <div class="movie-details-genres">
            <div v-for="genre in movie.genres" class="movie-details-genre">{{ genre}}</div>
          </div>
          <div class="movie-details-description">
            <div>{{ movie.description }}</div>
          </div>
          <div class="movie-details-ratings">
            <div class="movie-details-text">
               <div>Rating: {{ movie.rating }}/5</div>
            </div>
            <div class="movie-details-star">
               <div v-for="star in movie.rating">⭐️</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<style>

 .card_container{
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
 }

 .movie-card{
  margin: 10px;
  width: 300px;
 }

 .movie-image{
  width: 300px;
  height: 400px;
  overflow: hidden;
  border-radius: 5% 5% 0% 0%;
 }


 .movie-details{
  padding:10px;
  background-color: white;
  height: 250px;
  border-radius: 0% 0% 5% 5%;
 }

 .movie-details-title{
  font-size: 20px;
  font-weight: bold;
 }

 .movie-details-genres{
  display: flex;
  flex-direction: row;
 }

 .movie-details-genre{
  margin: 3px;
  background-color: blueviolet;
  border-radius: 50px;
  padding-left: 10px;
  padding-right: 10px;
  color:white
 }

 .movie-details-description{
  font-size: 15px;
  height: 100px;
 }





 .movie-details-ratings{

  margin-top: 20px;
  display: flex;
  flex-direction: row;
 }

 .movie-details-text{
  margin-right: 5px;
 }

 .movie-details-star{
  display: flex;
  flex-direction: row;
 }


 


</style>
