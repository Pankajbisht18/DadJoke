<template>
  <div>
   <h2>Welcome to the best Corny dad jokes app on the web</h2>
  </div>
</template>

<script>

export default {
  layout: 'jokes',
  head(){
    return{
      title: 'Welcome To The Dad Jokes',
      meta:[
        {
          hid: 'description',
          name: 'description',
          content: 'Best palce for corny dad jokes'
        }
      ]
    }
  }
}
</script>

