<template>
    <div>
        <h1>About DadJoke</h1>
        <p>This is an app that displays corny dad jokes</p>
    </div>
</template>

<script>
export default {
    head(){
        return{
            title: 'About the App',
            meta:[
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best palce for corny dad jokes'
                }
            ]
        }
    },
    layout: 'jokes'
}
</script>