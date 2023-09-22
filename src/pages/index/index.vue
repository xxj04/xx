<script setup lang="ts">
//
import CustomNavbar from '@/components/CustomNavbar.vue'
import { onLoad } from '@dcloudio/uni-app'
import { getHomeBanner } from '@/services/home'
import { ref } from 'vue'
import type { BannerItem } from '@/types/home'

const bannerlist = ref<BannerItem[]>([])
const getHomeBannerdata = async () => {
  const res = await getHomeBanner()
  bannerlist.value = res.result
}

onLoad(() => {
  getHomeBannerdata()
})
</script>

<template>
  <CustomNavbar></CustomNavbar>
  <XtxSwiper :list="bannerlist" />
  <view> index </view>
</template>

<style lang="scss"></style>
