<script>
  import { onMount } from "svelte";
  import Header from "../components/Header.svelte";
  import Main from "../components/Main.svelte";
  import TimeLine from "../components/TimeLine.svelte";
  import Sidebar from "../components/Sidebar.svelte";

  let data = {};
  const RICK = "https://rickandmortyapi.com/api/character/1";
  const API =
    "https://rickandmortyapi.com/api/character/1,8,15,19,22,48,56,69,72,74,78,82,86,103,119";

  onMount(async () => {
    const response = await fetch(API);
    data = await response.json();
  });
</script>

<Header />
<Main>
  <TimeLine posts={data} />
  <Sidebar results={data.results} />
</Main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Lato:wght@300;400&display=swap");
  @import url("https://fonts.googleapis.com/css2?family=Pacifico&display=swap");

  :global(body) {
    background-color: #fafafa;
    color: rgba(38, 38, 38, 0.7);
    font-family: "Lato", sans-serif;
    margin: 0;
    padding: 0;
  }
  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
  /* Dack Mode */
  :global(.Main.dark-mode, .Main.dark-mode
      .Share, .Header-container.dark-mode, .Sidebar.dark-mode .Stories) {
    background-color: #1d3040 !important;
    color: #bfc2c7;
  }
  :global(.Card.dark-mode, .Main.dark-mode .Share, .Header.dark-mode
      .Header-container, .Sidebar.dark-mode .Stories) {
    background-color: #1d3040 !important;
    border: 1px solid rgb(56, 68, 77) !important;
  }
  :global(.Card.dark-mode h2, .Card.dark-mode h3, .Sidebar.dark-mode h2) {
    color: white !important;
  }
  :global(.Card.dark-mode span, .Main.dark-mode
      .Share
      a, .Header.dark-mode, .Header.dark-mode i, .Sidebar.dark-mode
      .Stories
      span) {
    color: rgb(136, 153, 166) !important;
  }
  :global(.Card.dark-mode .Comments-add) {
    border-top: 1px solid rgb(56, 68, 77) !important;
  }
  :global(.Card.dark-mode .Comments-add input, .Card.dark-mode
      .Comments-add
      ::placeholder) {
    background-color: transparent !important;
    color: rgb(136, 153, 166) !important;
  }

  :global(.Card.dark-mode .Comments-add button) {
    color: #02c009 !important;
  }
</style>
