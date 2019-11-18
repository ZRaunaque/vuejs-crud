<template>
  <div>
    <div class="TopContainer">
      <input type="search" placeholder="Search by Name..." />
    </div>
    <Table
      :tutorial="tutorials"
      @EditClick="EditClicked"
      @DeleteClick="DeleteClicked"
      v-if="!selectedTutorial"
    ></Table>
    <TutorialEdit
      v-else-if="selectedTutorial"
      :selectedTutorial="selectedTutorial"
      @UpdateTutorial="UpdateTutorial"
      @removeSelection="removeSelection"
    ></TutorialEdit>
    <TutorialDelete v-else></TutorialDelete>
  </div>
</template>
<script>
import tutorials from "@/data.js";
import Table from "./Table.vue";
import TutorialEdit from "./TutorialEdit.vue";
// import TutorialDelete from "./TutorialDelete.vue";
export default {
  name: "Home",
  components: {
    Table,
    TutorialEdit
    // TutorialDelete
  },
  data() {
    return {
      tutorials,
      selectedTutorial: null
    };
  },
  methods: {
    EditClicked(val) {
      this.selectedTutorial = val;
    },
    removeSelection() {
      this.selectedTutorial = null;
    },
    UpdateTutorial() {
      const id = this.tutorials.findIndex(
        x => x.id == this.selectedTutorial.id
      );
      if (id > -1) {
        this.tutorials.splice(id, 1, this.selectedTutorial);
      }
      this.selectedTutorial = null;
    },
    DeleteClicked() {}
  }
};
</script>

