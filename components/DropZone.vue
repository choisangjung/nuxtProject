<template>
  <div 
    @dragenter.prevent="toggleActive" 
    @dragleave.prevent="toggleActive" 
    @dragover.prevent
    @drop.prevent="toggleActive"
    :class="{'active-dropzone': active}"
    class="dropzone"
  >
    <span>Drag or Drop File</span>
    <span>OR</span>
    <label for="dropzoneFile">Select File</label>
    <input type="file" id="dropzoneFile" class="dropzoneFile"/>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'DropZone',
  setup () {
    const active = ref(false)	// 영역 인식 제어용
    const toggleActive = () => {	// 영역 인식 제어용
      active.value = !active.value		
    }
    return { active, toggleActive}
  }
}
</script>

<style scoped lang="scss" >
    .dropzone{
        width: 400px;
        height: 200px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        row-gap: 16px;
        border: 2px dashed #41b883;
        background-color: #fff;
        transition: 0.3s ease all;
    }
</style>