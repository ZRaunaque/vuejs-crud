<template>
  <div class="TutorialDelete">
    <h2>
      Delete Tutorial
      <mark>{{ deleteTutorialData.name }}</mark>
    </h2>
    <p>Are you sure!</p>
    <form class="TutorialForm" action>
      <div class="FormButtons">
        <input
          class="Button DangerButton"
          type="button"
          value="Delete"
          @click.prevent="DeletTutorial"
        />
        <input class="Button" type="button" value="Cancel" @click.prevent="BacktoHome" />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "TutorialDelete"
};
</script>

