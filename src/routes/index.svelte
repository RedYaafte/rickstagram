<script context="module">
  const RICK = "https://rickandmortyapi.com/api/character/1";
  const API =
    "https://rickandmortyapi.com/api/character/1,8,15,19,22,48,56,69,72,74,78,82,86,103,119";

  export async function preload() {
    const data = await this.fetch(API).then((r) => r.json());
    return { data };
  }
</script>

<script>
  import Main from "../components/Main.svelte";
  import TimeLine from "../components/TimeLine.svelte";
  import Sidebar from "../components/Sidebar.svelte";

  export let data;
</script>

<svelte:head>
  <title>Rickstagram</title>
</svelte:head>

<Main>
  <TimeLine posts={data} />
  <Sidebar results={data.results} />
</Main>
