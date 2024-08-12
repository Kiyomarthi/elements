<template>
  <item1 @setCellphone="log" :title="title" :text="text" :img-address="imgAddress"></item1>
</template>

<script>
import item1 from './elements/heading/item-1'
export default {
  components: {
    item1
  },
  data() {
    return {
      title: 'خدمات طراحی سایت',
      text: 'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ، و با استفاده از طراحان گرافیک است، چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است، و برای شرایط فعلی تکنولوژی مورد نیاز، و کاربردهای متنوع با هدف بهبود ابزارهای کاربردی می باشد، کتابهای زیادی در شصت و سه درصد گذشته حال و آید.',
      imgAddress: '../../../../public/image.png'
    }
  },
  methods: {
    log(value) {
      console.log(value)
    }
  }
}
</script>
