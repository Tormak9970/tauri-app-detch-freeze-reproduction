<script lang="ts">
  import { http, fs, path } from "@tauri-apps/api";

  async function fetchProblematicImage() {
    console.log("Starting Problematic Image Download...");
    const imageURL = "https://cdn2.steamgriddb.com/file/sgdb-cdn/grid/e13967b41085b037a83173b3e0f8dcba.png";
    const localImagePath = await path.join(await path.desktopDir(), "broken-image-download.png");

    const imageData = await http.fetch<Uint8Array>(imageURL, {
      method: "GET",
      responseType: 3
    });
      
    await fs.writeBinaryFile(localImagePath, imageData.data);
    console.log("Download Complete!");
  }

  async function fetchWorkingImage() {
    console.log("Starting Working Image Download...");
    const imageURL = "https://cdn2.steamgriddb.com/file/sgdb-cdn/grid/18a8b3fbdf430fc0b02a7a0b68ddcfd3.webp";
    const localImagePath = await path.join(await path.desktopDir(), "working-image-download.webp");

    const imageData = await http.fetch<Uint8Array>(imageURL, {
      method: "GET",
      responseType: 3
    });
      
    await fs.writeBinaryFile(localImagePath, imageData.data);
    console.log("Download of Working Image Complete!");
  }
</script>

<div>
  <div class="row">
    <button on:click={fetchProblematicImage} style="margin-right: 14px;">
      Test Broken Fetch
    </button>
    <button on:click={fetchWorkingImage}>
      Test Working Fetch
    </button>
  </div>
</div>