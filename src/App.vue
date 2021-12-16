<template>
  <div>导航栏 | 
  <router-link to="/">HelloWorld</router-link> | 
  <router-link to="/test">Test</router-link></div>
  <hr/>
  <router-view />
</template>

<script>
export default {
  name: 'App',
}
</script>