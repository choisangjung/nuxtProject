<template>
  <div class="home">
    <h1>Drag Or Drop</h1>
    <drop-zone @drop.prevent="drop" @change="selectedFile"></drop-zone>
    <span class="file-info">File: {{ dropzoneFile.name }}</span>
  </div>
</template>

<script>
import { ref } from 'vue'
import DropZone from '@/components/DropZone'

export default {
  name: 'Home',
  components: {
      DropZone
  },
  setup () {
    let dropzoneFile = ref('')	// ref를 통해 dropzoneFile이라는 변수로 drop-zone 컴포넌트에 데이터를 공유해준다.
    
    // drop : 파일을 끌고와 영역 안에 해당 파일을 놓았을 경우 발생하는 이벤트.
    const drop = (e) => {
      dropzoneFile.value = e.dataTransfer.files[0] 		// dataTransfer이라는 js의 기능을 사용하여 file의 첫번째를 인식
    }

    const selectedFile = () => {
      dropzoneFile.value = document.querySelector('#dropzoneFile').files[0]	 // DropZone.vue에 있는 input type="file" 태그
      // 파일이 인식되었을 때, 파일의 이름을 찾아서 출력해줌.
    }

    return { dropzoneFile, drop, selectedFile }
  }
}
</script>