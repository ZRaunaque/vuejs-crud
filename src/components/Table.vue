<template>
  <div>
    <table class="TutorialsTable">
      <thead>
        <tr>
          <th>Name</th>
          <th>Description</th>
          <th>Price</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(tutorialItem, index) in tutorial" :key="index">
          <td>{{tutorialItem.name}}</td>
          <td>{{tutorialItem.description}}</td>
          <td>Rs {{tutorialItem.price}}</td>
          <td>
            <input type="button" value="Edit" @click="$emit('EditClick', tutorialItem)" />
            <input type="button" value="Delete" @click="$emit('DeleteClick')" />
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "Table",
  props: {
    tutorial: {
      type: Array,
      required: true
    }
  }
};
</script>
