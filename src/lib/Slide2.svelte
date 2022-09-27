<script lang="ts">
  import { Card, Chip } from "svelte-materialify";

  export let config: Config;
</script>

<div class="main">
  <Card raised>
    <div class="center">
      <img src="/images/breaking-news.gif" alt="" />
    </div>
    <div class="padding">
      <h5 class="text-h5">Merhaba {config.name}</h5>
      <div class="br" />
      <hr />
      <div class="br" />
      <div>Galiba bugün birinin özel günü, acaba kimin?</div>
      <h4 class="center">🤔</h4>
      <div class="br" />
      <div class="center">
        <Chip class="red">İpucu: Kişinin ismi {config.name} ile başlıyor.</Chip>
      </div>
    </div>
  </Card>
</div>
