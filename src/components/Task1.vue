<template>
    <div id="slider">
        <Slider1 :image="images[chosenImage]"/>
        <div class="previous" @click="previous()"></div>
        <div class="next" @click="next()"></div>
    </div>
</template>
    
<script>

import Slider1 from "@/components/Slider1.vue";

export default {
    name: "Task1",
    components : {
        Slider1
    },
    data(){
        return{
            
            images:[
                {
                    id:0,
                    path:require('../assets/notus-task1-img1.jpg'),
                },
                {
                    id:1,
                    path:require('../assets/notus-task1-img2.jpg'),
                },
                {
                    id:2,
                    path:require('../assets/notus-task1-img3.jpg'),
                }
            ],
            chosenImage:0,
            
        }
    },
    methods : {
        previous(){
            this.moveLeft();
        },
        next(){
            this.moveRight()
        },
        moveLeft(){
            let flag = this.chosenImage;
            flag--;
            if(flag<0){
                flag = (this.images.length - 1);
            }
            this.chosenImage = flag;
        },
        moveRight(){
            let flag = this.chosenImage;
            flag++;
            if(flag >= this.images.length ){
                flag = 0;
            }
            this.chosenImage = flag;
        }
    }
    
}
</script>

<style>
#slider{
    position: relative;
    overflow: hidden;
}

#slider .previous,#slider .next{
    position: absolute;
    top: 50%;
    border: 20px solid transparent;
}
#slider .previous{
    border-right-color: green;    
    z-index: 1;
}
#slider .next{
    right:0;
    border-left-color: green;
}
#slider .squares{
    position: absolute;
    bottom: 0;
    left: calc( 50% - 75px);
}
#slider .squares div{
    height:20px;
    width:20px;
    margin-right: 10px;
    display: inline-block;
    background-color:yellow;
    border-radius:50%;
}
</style>
