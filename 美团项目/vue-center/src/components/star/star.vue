<template>
  <div class="star" :class="`star-${size}`">
  <span class="star-item" v-for="(sc, index) in starClasses" 
  :key="index" :class="sc"></span>
  </div>
</template>
<script>
const CLASS_ON = 'on' 
const CLASS_HALF = 'half' 
const CLASS_OFF = 'off' 
export default {
props: { score: Number, size: Number },

computed: { 
  starClasses () {
     const scs = [] 
     const {score} = this 
     const scoreInteger = Math.floor(score)
     for (let i = 0; i< scoreInteger; i++) { scs.push(CLASS_ON) }
     if(score*10-scoreInteger*10>=5) { scs.push(CLASS_HALF) }
      while(scs.length<5) { scs.push(CLASS_OFF) }return scs }
}
}
</script>
<style lang="stylus" rel="stylesheet/stylus">
                  .star {
                    float: left;
                    font-size: 0;

                    .star-item {
                      display: inline-block;
                      background-repeat: no-repeat;
                    }

                    &.star-24 {
                      .star-item {
                        width: 10px;
                        height: 10px;
                        margin-right: 3px;
                        background-size: 10px 10px;
                        

                        &:last-child {
                          margin-right: 0px;
                        }

                        &.on {
                          background-image: url(./images/star24_on.png);
                          
                        }

                        &.half {
                          background-image: url(./images/star24_half@2x.png);
                        }

                        &.off {
                          background-image: url(./images/star24_off@2x.png);
                        }
                      }
                    }

                    &.star-36 {
                      .star-item {
                        width: 15px;
                        height: 15px;
                        margin-right: 6px;
                        background-size: 15px 15px;

                        &:last-child {
                          margin-right: 0px;
                        }

                        &.on {
                          background-image: url(./images/star36_on@2x.png);
                        }

                        &.half {
                          background-image: url(./images/star36_half@2x.png);
                        }

                        &.off {
                          background-image: url(./images/star36_off@2x.png);
                        }
                      }
                    }

                    &.star-48 {
                      .star-item {
                        width: 20px;
                        height: 20px;
                        margin-right: 22px;
                        background-size: 20px 20px;

                        &:last-child {
                          margin-right: 0px;
                        }

                        &.on {
                          background-image: url(./images/star48_on@2x.png);
                        }

                        &.half {
                          background-image: url(./images/star48_half@2x.png);
                        }

                        &.off {
                         background-image: url(./images/star48_half@2x.png);
                        }
                      }
                    }
                  }
</style>