<template lang="pug">
  .card-wrapper
    .card(@click="handleView($event)" :class="{'open': card.open}" :style="styleObject")
      .card-top
        .card-img(:style="{'background-image': 'url('+ require('../assets/img'+ card.img)+')'}")
        .card-title 
          h2 {{ card.title }}
      .card-description
        p {{ card.description }}

</template>

<script>
 export default {
   name:'Card',
   props: ['card'],
   data () {
     return {
       styleObject: {
         transform: 'translate(0px, 0px)',
       }
     }
   },
   methods: {
     handleView(el) {
       this.card.open = !this.card.open;
       let viewportOffeset = el.target.getBoundingClientRect();
       console.log(viewportOffeset);
       
       if(this.card.open) {
         document.body.top = '-' + window.scrollY + 'px';
         document.body.position = 'fixed';

         this.styleObject.transform = 'translate('+ viewportOffeset.left * -1 +'px, ' + viewportOffeset.top * -1 +'px)';
       }else {
         this.styleObject = {
          transform: 'translate(0px, 0px)',
          };

          let scrollY = document.body.style.top;
          document.body.top = '';
          document.body.position = '';
          window.scrollTo(0, parseInt(scrollY) * -1);
       }
     }
   }
  }
</script>

<style lang="scss" scoped>
  .card-wrapper{
    width: 100%;
    height: 450px;
    margin-bottom: 20px;
    .card {

      position: relative;
      border-radius: 20px;
      width: 100%;
      height: 450px;
      border: 1px solid #fff;
      background: #efefef;
      overflow: hidden;
      cursor: pointer;
      z-index: 1;
      transition: all .5s  cubic-bezier(.6, 0, .45, 1.3);

      &.open {
        z-index: 100;
        border-radius: 0;
        border: 0;
        width: 100vw;
        height: 100vh;
      }

      .card-top, .card-title, .card-description, .card-img {
        pointer-events: none;
      }

      .card-top {

        position: relative;
        background-color: #fff;

        .card-img {
          width: 100%;
          height: 450px;
          background-position: center;
          background-size: cover;
        }

        .card-title {

          position: absolute;
          bottom: 0;
          padding: 5px 25px;
          font-size: 10px;
          width: 100%;
          height: 40px;
          color: #fff;
          background: linear-gradient(270deg,#154284,#cd122d);
          display: flex;
          align-items: center;
          justify-content: center;

        }
      }

      .card-description {
        padding: 20px;
      }
    }
      
  }
    
</style>