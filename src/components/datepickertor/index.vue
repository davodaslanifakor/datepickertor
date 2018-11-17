<template>
    <div :class="perfix">
        <div :class="perfix+'-header'">
            <div :class="perfix+'-arrow-right'">
                <img src="./icons/right-arrow.svg" alt="datepickertor-arrow-right">
            </div>
            <div :class="perfix+'-title'">
                اردیبهشت ۱۳۹۷
            </div>
            <div :class="perfix+'-arrow-left'">
                <img src="./icons/left-arrow.svg" alt="datepickertor-arrow-left">
            </div>
        </div>
        <div :class="perfix+'-body'">
            <div :class="perfix+'-name-day'">
                <span v-for="(item,index) in nameDay" :key="index" :class="perfix+'-name'">
                    {{ item }}
                </span>
            </div>
            <div :class="perfix+'-weeks'" v-for="item in weeks">
                <div :class="perfix+'-day'" v-for="day in item">
                    {{day}}
                </div>
            </div>
        </div>
        <div :class="perfix+'-footer'">
            <button :class="perfix+'-select-date'">
                انتخاب تاریخ
            </button>
        </div>
    </div>
</template>

<script>
import './css/fontiran.css'
export default {
  props: {
    perfix: {
      type: String,
      default: "datepickertor"
    },
    nameDay: {
      type: Array,
      default: ["ش", "ی", "د", "س", "چ", "پ", "ج"]
    }
  },
  data() {
      return {
          weeks: [
              [
                  1,2,3,4,5,6,7
              ],
              [
                  8,9,10,11,12,13,14
              ],
              [
                  16,17,18,19,20,21,22
              ],
              [
                  23,24,25,26,27,28,29
              ],
              [
                  30,31,1,2,3,4,5,6
              ],
          ]
      }
  },
};
</script>

<style lang="stylus" scoped>
.datepickertor
    display flex
    flex-direction column
    width 100%
    width 300px
    font-family iranyekan
    &-header
        display flex
        flex-direction row-reverse
        justify-content space-between
        align-items center
        width 100%
    &-title
        font-weight 400
        font-size 18px
    &-arrow-left, &-arrow-right
        display flex
        justify-content center
        align-items center
        width 32px
        height 32px
        border-radius 100%
        background-color rgb(242, 242, 242)
    &-name-day
        display flex
        justify-content space-around
        flex-direction row-reverse
        margin-top 10px
        margin-bottom 5px
    &-name
        color #009d7e
        font-weight bold
        flex 1 1
        text-align center
    &-weeks
        display flex
        justify-content space-around
        flex-direction row-reverse
        margin-bottom 5px
    &-day 
        text-align center
        font-family roboto
    &-footer
        display flex
        margin-top 15px
    &-select-date
        width 100%
        height: 38px;
        border-radius: 5px;
        box-shadow: 0 2px 4px 0 rgba(0, 150, 135, 0.33);
        background-image: linear-gradient(to top, rgb(0, 150, 136), rgb(0, 165, 114));
        color #ffffff
        font-family iranyekan
        border none 
</style>
