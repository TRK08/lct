<template>
  <div class="home-page">

    <n-tabs type="segment">
      <n-tab-pane name="video" tab="Видео">
        <UploadFile />
      </n-tab-pane>
      <n-tab-pane name="link" tab="RTSP ссылка">
        <RTSPLink />
      </n-tab-pane>
    </n-tabs>

    <n-modal v-model:show="videoPath"  preset="card" style="width: fit-content">
      <n-card >Видео обрабатывается</n-card>
       <VideoPlayer v-if="videoPath" :path="videoPath" />
    </n-modal>


<!--    <video controls>-->
<!--      <source src="http://45.9.27.201/api/v1/ml/get_video?id=b8498b24-990b-4e76-afdc-dc371b6430a7" >-->
<!--    </video>-->


  </div>
</template>

<script setup lang="ts">
import {storeToRefs} from "pinia";
import { ArchiveOutline } from '@vicons/ionicons5'
import {useVideoStore} from "@/stores/video";
import UploadFile from "@/components/UploadFile.vue";
import VideoPlayer from "@/components/VideoPlayer.vue";
import RTSPLink from "@/components/RTSPLink.vue";

const {fetchStatus, videoPath} = storeToRefs(useVideoStore())


</script>

<style lang="scss">
.home-page {
  &__upload {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 200px;
  }
  .n-card {
    border-radius: 1rem;
  }
}
</style>
