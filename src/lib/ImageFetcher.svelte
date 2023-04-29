<script lang="ts">
  import { http, fs, path } from "@tauri-apps/api";

  async function fetchProblematicImage() {
    console.log("Starting download...");
    const imageURL = "https://cdn2.steamgriddb.com/file/sgdb-cdn/grid/e13967b41085b037a83173b3e0f8dcba.png";
    const localImagePath = await path.join(await path.desktopDir(), "app-freeze-download-test.png");

    const imageData = await http.fetch<Uint8Array>(imageURL, {
      method: "GET",
      responseType: 3
    });
      
    await fs.writeBinaryFile(localImagePath, imageData.data);
    console.log("Download Complete!");
  }
</script>

<div>
  <div class="row">
    <button on:click={fetchProblematicImage}>
      Test Fetch
    </button>
  </div>
</div>