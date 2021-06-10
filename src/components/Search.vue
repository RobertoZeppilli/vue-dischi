<template>
  <div class="genres-form">
    <form id="genre">
      <label for="genres">Select by genres</label>
      <select
        v-model="selected"
        name="genrelist"
        id="genres"
        form="genre"
        @change="$emit('selectGenre', selected)"
      >
        <option disabled value="">Please select one</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        <option value="All">All</option>
      </select>
    </form>
  </div>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      selected: ""
    };
  }
};
</script>

<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

.genres-form {
  @include flex($type: "between");
  margin: 0 10px;
  color: $primaryText;

  select {
    margin-left: 10px;
  }
  #artists {
      margin-bottom: 10px;
  }
}
</style>