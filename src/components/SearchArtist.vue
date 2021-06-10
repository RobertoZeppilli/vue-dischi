<template>
  <div class="artist-form">
    <form id="artist">
      <label for="artists">Select by artists</label>
      <select
        v-model="selectedArtist"
        name="artistlist"
        id="artists"
        form="artists"
        @change="$emit('selectArtist', selectedArtist)"
      >
        <option disabled value="">Please select one</option>
        <option value="Bon Jovi">Bon jovi</option>
        <option value="Queen">Queen</option>
        <option value="Sting">Sting</option>
        <option value="Steve Gadd Band">Steve Gadd Band</option>
        <option value="Iron Maiden">Iron Maiden</option>
        <option value="Eric Clapton">Eric Clapton</option>
        <option value="Deep Purple">Deep Purple</option>
        <option value="Metallica">Metallica</option>
        <option value="Dave Weckl">Dave Weckl</option>
        <option value="Michael Jacjson">Michael Jacjson</option>
        <option value="All">All</option>
      </select>
    </form>
  </div>
</template>

<script>
export default {
  name: "SearchArtist",
  data() {
      return {
          selectedArtist: ''
      }
  }
};
</script>

<style lang="scss" scoped>
select {
    margin-left: 10px;
}
</style>