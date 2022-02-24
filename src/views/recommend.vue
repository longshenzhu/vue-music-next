<template>
  <div class="recommend">
      <slider v-if="sliders.length" :sliders="sliders"></slider>
      推荐页面
  </div>
</template>

<script>
import { getRecommend } from "../server/recommand"
import Slider from "../components/base/slider/slider"

export default {
    name: "recommend",
    data() {
        return {
            sliders: [],
            albums: [],
        }
    },
    async created() {
        const result = await getRecommend()
        debugger
        this.sliders = result.sliders
        this.albums = result.albums
        console.log(result)
    },
    components: {
        Slider
    }
}
</script>

<style>

</style>
