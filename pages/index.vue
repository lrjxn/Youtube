<template>
<div>
  <v-chip-group active-class="blue white--text" v-model="selection" column class="boxtext">
          <v-chip>All</v-chip>
          <v-chip>Music</v-chip>
          <v-chip>Live</v-chip>
          <v-chip>Fireplace</v-chip>
          <v-chip>Game Shows</v-chip>
          <v-chip>Ambient music</v-chip>
          <v-chip>Gaming</v-chip> 
          <v-chip>Recently uploaded</v-chip> 
          <v-chip>Ambient music</v-chip>
          <v-chip>Gaming</v-chip> 
          <v-chip>Recently uploaded</v-chip>
          <v-chip>Music</v-chip>
          <v-chip>Live</v-chip>
          <v-chip>Fireplace</v-chip>
          <v-chip>Game Shows</v-chip>
          <v-chip>Ambient music</v-chip>
        </v-chip-group>

<v-row >
      <v-col
        v-for="n in 40"
        :key="n"
        cols="3"
      >
<v-card class="box1">
      <v-img height="250" src="http://placekitten.com/g/380/400"></v-img>
   <v-card-title> <img src="http://placekitten.com/g/50/50"  class="pfp">kass</v-card-title>
      <v-card-text>
        <v-row class="mx-0">
          <div class="grey--text ms-1">
          Kassike67
          </div>
        </v-row>
      <v-row>
        <div class="grey--text ms-4" > 229K views · 1 day ago</div></v-row>
      </v-card-text>
    </v-card>
      </v-col>
    </v-row>
</div>
</template>
