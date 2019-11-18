<template>
  <div class="TutorialEdit">
    <h2>
      Edit Tutorial
      <mark>{{selectedTutorial.name}}</mark>
    </h2>
    <form class="TutorialForm" action>
      <div class="InputField">
        <label for="tutorialname">Name</label>
        <input type="text" name="tutorialname" required v-model="selectedTutorial.name" />
      </div>
      <div class="InputField">
        <label for="tutorialdescription">Description</label>
        <textarea
          name="tutorialdescription"
          rows="10"
          required
          v-model="selectedTutorial.description"
        ></textarea>
      </div>
      <div class="InputField">
        <label for="tutorialprice">Price in Rs(numbers only)</label>
        <input type="number" name="tutorialprice" required v-model="selectedTutorial.price" />
      </div>
      <div class="FormButtons">
        <input
          class="Button PrimaryButton"
          type="button"
          value="Update Tutorial"
          @click.prevent="$emit('UpdateTutorial')"
        />
        <input
          class="Button"
          type="button"
          value="Cancel"
          @click.prevent="$emit('removeSelection')"
        />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "TutorialEdit",
  props: {
    selectedTutorial: {
      type: Object,
      required: true
    }
  }
};
</script>

