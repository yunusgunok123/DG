<script lang="ts">
  import { Card } from "svelte-materialify";

  export let config: Config;
</script>

<div class="main">
  <Card raised>
    <div class="center">
      <div class="stack">
        <img src="/faces/{config.file}" alt="" />
        <img class="crown" src="/images/crown.png" alt="" />
        <img class="confetti" src="/images/confetti.gif" alt="" />
      </div>
    </div>
    <div class="padding">
      <h5 class="text-h5">Doğum Günün Kutlu Olsun</h5>
      <div class="br" />
      <hr />
      <div class="br" />
      <div>Biliyorum tacı çok zarif bir şekilde koymuşum.</div>
      <div class="br" />
      <div>Umarım yeni yaşında bütün dileklerin gerçekleşir.</div>
    </div>
  </Card>
</div>
