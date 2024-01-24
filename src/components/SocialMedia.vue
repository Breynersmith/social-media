<template>
    <div class="bg-[#242424] p-5 w-[70%] max-w-[400px] text-center text-white font-[myFont] flex flex-col gap-4 justify-center items-center rounded-xl mx-auto mt-5">
       <div class="w-[10rem] h-[10rem] rounded-full">
        <img 
        class="w-full h-full rounded-full"
        src="/perfil.png" alt="">
       </div>
       <article class="w-[100%]">
        <h1 class="text-lg font-bold font-[myFont]">Breyner Ustariz</h1>
        <p class="text-[#A3C14C]" >Bogota, Colombia</p>
        <p>Frontend Developer</p>
        
        <div
        class="flex gap-4 flex-col py-2">

            <a 
            @click="handleActive"
            v-for="link in dataLink"
            :class="btnActive ? 'active' : ''"
            class="bg-[#363636] p-2 rounded-md hover:bg-[#A3C14C] hover:text-black transition-all duration-300"
            :href="link.link" target="_blank">{{ link.name }}</a>

        </div>
       </article>
    </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const dataLink = [
        {
            name: 'GitHub',
            link: 'https://github.com/Breynersmith'

        },
        {
            name: 'Fronted Mentor',
            link: 'https://www.frontendmentor.io/profile/Breynersmith'
        },
        {
            name: 'Linkedin',
            link: 'https://www.linkedin.com/in/breynerustariz/'
        },
        {
            name: 'Twitter',
            link: 'https://twitter.com/BreynerUstariz'
        },
        {
            name: 'Instagram',
            link: 'https://www.instagram.com/breynerustariz/'
        }
    ]


onMounted(()=> {

    const font = new FontFace('myFont.ttf', 'url(/fonts/myFont.ttf)')
    font.load().then(font => {
        document.fonts.add(font)
    })

    
})



const handleActive = (e) => {
    const btnActive = ref(false)
    btnActive.value = true
    return btnActive
}


</script>

<style scoped>
.active{
    background-color: #A3C14C;
}
</style>