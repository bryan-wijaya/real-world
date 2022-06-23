 <template> 
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Hehehe</p>
    </Modal>
  </div>
  <div v-if="showModal2">
    <Modal theme="sale" @close="toggleModal2">
      <h1>TestSkill</h1>
      <p>test ae dah</p>
    </Modal>
  </div>
  
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModal2">Open Modal 2</button>
 </template>

<script>
import Modal from "./ModalDiv.vue";
export default {
  name: "Home",
  components: { Modal },
  data() {
    return {
      title: "TestSkill",
      showModal: false,
      showModal2: false,
    };
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal;
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2;
    }
  }
};
</script>