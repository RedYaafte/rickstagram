<script>
  import ToggleSwitch from "./ToggleSwitch.svelte";

  let styles = { darkMode: false };

  function toggle() {
    styles.darkMode = !styles.darkMode;
    console.log(styles.darkMode);
    window.document.querySelector(".Main").classList.toggle("dark-mode");
    window.document.querySelector(".Header").classList.toggle("dark-mode");
    window.document.querySelector(".Sidebar").classList.toggle("dark-mode");
    let card = window.document.querySelectorAll(".Card");

    let i;
    for (i = 0; i < card.length; i++) {
      card[i].classList.toggle("dark-mode");
    }
  }
</script>

<div class="Profile">
  <div class="Profile-content">
    <div class="Profile-avatar">
      <img
        src="https://pbs.twimg.com/profile_images/1378206127368892420/XQIo8Teo_400x400.jpg"
        alt="profile"
      />
    </div>
    <div class="Profile-info">
      <h2>redyafte</h2>
      <span>Yafté M.</span>
    </div>
    <div class="Profile-dark-mode">
      <ToggleSwitch on:click={toggle} />
    </div>
  </div>
</div>

<style>
  .Profile-content {
    display: flex;
    align-items: center;
  }
  .Profile-avatar img {
    width: 42px;
    height: 42px;
    border-radius: 50%;
  }
  .Profile-info {
    margin: 0 0 0 0.5em;
  }
  .Profile-info h2 {
    font-size: 14px;
    color: black;
    margin: 0;
    padding: 0;
  }
  .Profile-info span {
    font-size: 12px;
    font-weight: normal;
  }
  .Profile-dark-mode {
    margin-left: 25px;
  }
</style>
