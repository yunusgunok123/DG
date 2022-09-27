<script lang="ts">
  import { Button, Card } from "svelte-materialify";

  export let id: string;
</script>

<div class="main">
  <Card raised>
    <div class="center">
      <iframe
        src="https://www.youtube.com/embed/{id}"
        frameborder="0"
        title="YouTube video player"
      />
    </div>
    <div class="padding">
      <h4 class="text-h4">Dikkat</h4>
      <div class="br" />
      <hr />
      <div class="br" />
      <div>Lütfen başlamadan önce yukarıdaki Youtube videosunu başlat.</div>
      <div class="br" />
      <div>
        Sağ üstteki tuş ile açık/karanlık modu ayarlayabilirsin, aşağıdaki
        tuşlar ile de hareket edebilirsin.
      </div>
    </div>
  </Card>
</div>
