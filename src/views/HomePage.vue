<template>
  <div class="home-page">

    <n-tabs type="segment">
      <n-tab-pane name="video" tab="Видео">
        <UploadFile />
      </n-tab-pane>
      <n-tab-pane name="link" tab="RTSP поток">
        <RTSPLink />
      </n-tab-pane>
    </n-tabs>

    <n-modal v-model:show="videoId"  preset="card" style="width: fit-content; min-width: 50vw">
      <VideoPlayer v-if="videoPath" :path="videoPath" />
      <n-result
          v-else
          status="info"
          description="Подождите, видео обрабатывается"
      >
        <template #footer>
          <n-spin size="large" />
        </template>
      </n-result>

    </n-modal>


  </div>
</template>

<script setup lang="ts">
import {storeToRefs} from "pinia";
import { ArchiveOutline } from '@vicons/ionicons5'
import {useVideoStore} from "@/stores/video";
import UploadFile from "@/components/UploadFile.vue";
import VideoPlayer from "@/components/VideoPlayer.vue";
import RTSPLink from "@/components/RTSPLink.vue";
import {computed} from "vue";

const {fetchStatus, videoId, videoPath} = storeToRefs(useVideoStore())



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
