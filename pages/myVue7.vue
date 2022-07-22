<template>
  <div>
    <h1>MODAL-POPUP</h1>
    <button class="btn btnHome" @click="goHOME">HOME</button>
    <div>
      <template>
        <v-container>
          <v-data-table
            class="row-cursor-pointer"
            style="width: 100%"
            :headers="headers"
            :items="contents"
            sort-by="itemcode"
            @click:row="handleClick"
          >
          </v-data-table>
        </v-container>
      </template>
    </div>

    <div class="example-modal-window">
      <p>버튼을 누르면 모달 대화 상자가 열립니다.</p>
      <button @click="openModal">열기</button>

      <!-- 컴포넌트 MyModal -->
      <MyModal @close="closeModal" v-if="modal">
        <!-- default 슬롯 콘텐츠 -->
        <p>Vue.js Modal Window!</p>
        <div><input v-model="message" /></div>
        <!-- /default -->
        <!-- footer 슬롯 콘텐츠 -->
        <template slot="footer">
          <button @click="doSend">제출</button>
        </template>
        <!-- /footer -->
      </MyModal>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import myModal from './components/myModal.vue'
export default {
  data() {
    return {
      headers: [
        { text: "시스템번호", align: "center", sortable: false, value: "tkey" },
        {
          text: "시험시스템번호",
          align: "center",
          sortable: false,
          value: "qtsmatkey",
        },
        {
          text: "자재코드",
          align: "center",
          sortable: false,
          value: "itemcode",
        },
        {
          text: "자재내역",
          align: "center",
          sortable: false,
          value: "itemname",
        },
        { text: "제조번호", align: "center", sortable: false, value: "lotno" },
        { text: "관리번호", align: "center", sortable: false, value: "charg" },
        {
          text: "상태표기값",
          align: "center",
          sortable: false,
          value: "statustext",
        },
        {
          text: "요청자",
          align: "center",
          sortable: false,
          value: "crtusername",
        },
        {
          text: "요청사유",
          align: "center",
          sortable: false,
          value: "crtnote",
        },
        { text: "비고", align: "center", sortable: false, value: "note" },
        {
          text: "삭제FLAG",
          align: "center",
          sortable: false,
          value: "delflag",
        },
      ],
      contents: [],
    };
  },
  methods: {
    goHOME() {
      this.$router.push("/");
    },
    async fetchThing() {
      const response = await axios
        .get("http://localhost:3080/api/GETPRCOALIST")
        .then((res) => {
          this.contents = res.data;
        });
    },
    handleClick(value) {
      console.log(value);
      this.$refs["modal"].show();
    },
  },
  created() {
    this.fetchThing();
  },
};
</script>

<style scoped>
.row-cursor-pointer :deep(tbody tr :hover) {
  cursor: pointer;
}

.btn {
  text-decoration: none;
  padding: 20px 20px;
  font-size: 1.25rem;
  position: relative;
}

.btnHome {
  background: #000;
  color: #fff;
  border-radius: 30px;
  transition: transform 0.3s ease;
  box-shadow: 0 0 0 0 rgba(143, 64, 648, 0.5),
    10px -10px 25px 0 rgba(39, 200, 255, 0.5);
}

.btnHome:hover {
  cursor: pointer;
  transform: translateY(-0.25em);
}
</style>