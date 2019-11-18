<template>
  <div class="TutorialCreate">
    <h2>Add New Tutorial</h2>
    <form class="TutorialForm">
      <div class="InputField">
        <label for="tutorialname">Name</label>
        <input type="text" name="tutorialname" required v-model="tutorial.name">
      </div>
      <div class="InputField">
        <label for="tutorialdescription">Description</label>
        <textarea name="tutorialdescription" rows="5" required v-model="tutorial.description"></textarea>
      </div>
      <div class="InputField">
        <label for="tutorialprice">Price in Rs(numbers only)</label>
        <input type="number" name="tutorialprice" required v-model="tutorial.price">
      </div>
      <div class="FormButtons">
        <input class="Button PrimaryButton" type="button" value="Create Tutorial" @click.prevent="AddTutuorial">
        <input class="Button" type="button" value="Cancel" @click.prevent="BacktoHome">
      </div>
    </form>
  </div>
</template>

<script>
import tutorials from '@/data.js';
export default {
  name: 'TutorialCreate',
  data() {
    return {
      tutorials,
      tutorial: {
        name: '',
        description: '',
        price: ''
      }
    }
  },
  methods : {
    BacktoHome(){
      this.$router.push({ path: '/' })
    },
    AddTutuorial() {
      console.log(this.tutorial, "added tutroial")
      let tutorial = this.tutorial
      this.tutorials.push({
        id: Math.random().toString().split('.')[1],
        name:tutorial.name,
        description: tutorial.description,
        price: tutorial.price
      })
      // this.tutorials.push(this.tutorial)
      this.$router.push({name: 'Home'})
    }
  }
}
</script>

