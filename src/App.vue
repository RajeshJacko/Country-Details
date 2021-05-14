<template>
  <div id="app">
      <div id="nav">
        <router-link to = "/country/nepal">Nepal</router-link>
        <router-link to = "/country/brazil">Brazil</router-link>
        <router-link to = "/country/canada">Canada</router-link>
        <router-link to = "/country/china">China</router-link>
    </div>
    <router-view :key="$route.path"/>
  </div>
</template>

<style>

#nav{
  display:flex
}
#nav a {
margin:10px}
</style>
