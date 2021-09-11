<script>
  import Profile from "./Profile.svelte";
  import Stories from "./Stories.svelte";
  import Footer from "./Footer.svelte";

  export let results;
  console.log(results);
  // console.log(results[0]);
  // let name = results.filter((character) => "rick" in character.name);
  // console.log(name);
</script>

<div class="Sidebar">
  <div class="Sidebar-container">
    <Profile />
    <Stories />
    <Footer />
  </div>
</div>

<style>
  .Sidebar {
    position: relative;
    padding: 4.5em 0 0 0;
  }
  .Sidebar-container {
    position: fixed;
  }
</style>
