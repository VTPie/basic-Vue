<script setup>
    import { ref } from 'vue';
    
    const msg1=ref('This line is added by v-text.')
    const msg2=ref('This line is added by v-html.')
    const msg3=ref('Click button to hide me!')
    const msg4=ref('Case 1. Click button to move to next case.')
    const msg5=ref('Case 2. Click button to move to next case.')
    const msg6=ref('Case 3. Click button to move to next case.')
    const msg7=ref('Last case. Click button to move to next case.')
    const msg8=ref('Built-in directive list')
    const msg9=ref('Click button to enlarge this text.')
    const msg10=ref('Click button to change color for this text.')
    const msg11=ref('')


    const isShow=ref(true)
    const index=ref(0)
    function onChangeIndex(){
        if(index.value < 3){
            index.value++
        }
        else{
            index.value=0
        }
    }
    const arrDirective = ref([
        { msg: 'v-text' }, 
        { msg: 'v-html' },
        { msg: 'v-show' }, 
        { msg: 'v-if, v-else-if, v-if' },
        { msg: 'v-for' }, 
        { msg: 'v-on' },
        { msg: 'v-bind' }, 
        { msg: 'v-model' },
    ])
    const postFontSize = ref(1)
    const isBlue=ref(false)
</script>

<template>
    <h1>This is Built-in Directive component</h1>

    <h2>v-text</h2>
    <p v-text="msg1"></p>

    <h2>v-html</h2>
    <p v-html="msg2"></p>

    <h2>v-show</h2>
    <p v-show="isShow">{{ msg3 }}</p>
    <button @click="isShow = !isShow">Click me!</button>

    <h2>v-if, v-else, v-else-if</h2>
    <div v-if="index === 0">
        {{ msg4 }}
    </div>
    <div v-else-if="index === 1">
        {{ msg5 }}
    </div>
    <div v-else-if="index === 2">
        {{ msg6 }}
    </div>
    <div v-else>
        {{ msg7 }}
    </div>
    <button @click="onChangeIndex">Click me!</button>

    <h2>v-for</h2>
    <p>{{ msg8 }}</p>
    <ul>
        <li v-for="item in arrDirective">
            {{ item.msg }}
        </li>
    </ul>

    <h2>v-on</h2>
    <p :style="{ fontSize: postFontSize + 'em' }">{{ msg9 }}</p>
    <button @click="postFontSize += 0.1">Click me!</button>

    <h2>v-bind</h2>
    <p :class="{blue: isBlue}">{{ msg10 }}</p>
    <button @click="isBlue = !isBlue">Click me!</button>

    <h2>v-model</h2>
    <p>Message is: {{ msg11 }}</p>
    <input v-model.lazy="msg11" placeholder="edit me" />

</template>

<style>
    .blue{
        color: blue;
    }
</style>