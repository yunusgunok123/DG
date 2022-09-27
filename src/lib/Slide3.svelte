<script lang="ts">
  import { Button, Card, Chip } from "svelte-materialify";

  export let config: Config;

  const skull = "Ḍ̵̎ḯ̶̡k̶̛͈k̶̩̕á̴̧ṱ̴̌ ̵͈͐ė̸̱t̴̠̎ ̸̙̒o̶̞͠ ̷̞͠ş̸͕̉ů̸̬ ̵̄ͅa̷̰͘ñ̵͖ ̶̯̊s̸̘͐ẻ̴̤n̶͑͜i̴͍̎ ̸͍̇ǩ̴̲a̸̹̍m̶͉̀e̷͓͐ȑ̸̬a̸̲̔n̷͙̾ď̶̝à̴͇n̷̻͆ ̵̿ͅi̶̡͒z̶̼̔l̴̯̓i̴̬̐ý̴̳o̵̢̾r̸̝̉.̸̻̈";

  let message = "";
  const endMessage = config.message + " ";
  const len = endMessage.length;
  const duration = 3000;
  const interval = Math.round(duration / len);
  let isActive = false;
  let isShown = false;

  function event() {
    for (let i = 0; i < len; i++) {
      setTimeout(() => (message = endMessage.slice(0, i) + "_"), interval * i);
    }
    setTimeout(() => (isActive = true), duration + 500);
    setTimeout(
      () => ((isActive = false), (message = ""), (isShown = true)),
      duration + 1000
    );
  }

  setTimeout(event, 1000);
</script>

<div class="main">
  <Card raised>
    <div class="padding">
      <div class="left">
        <Button fab size="small" on:click={() => alert("Mesajlarıma bakama!")}
          >⫷</Button
        >
        <div class="br" />
        <div>
          <h6 class="text-h6">{config.name}</h6>
          <div class="text-caption">Çevrimiçi</div>
        </div>
      </div>
      <div class="br" />
      <hr />
      <div class="br" />
      <div class="center"><Chip>Dün</Chip></div>
      <div class="br" />
      <div class="left"><div class="recieve red">sjsjsjsjsj</div></div>
      <div class="br" />
      <div class="left">
        <div class="recieve red">Yunus çok mükemmelsin.</div>
      </div>
      <div class="br" />
      <div class="right"><div class="send blue">😳</div></div>
      <div class="br" />
      <div class="right"><div class="send blue">Biliyorum</div></div>
      <div class="br" />
      <div class="center"><Chip>Bugün</Chip></div>
      <div class="br" />
      {#if isShown}
        <div class="right message">
          <div class="send blue">{config.message}</div>
        </div>
      {:else}
        <div class="right hidden">
          <div class="send blue">Bu gizli bir mesaj.</div>
        </div>
      {/if}
      <div class="br" />
      <div class="inline">
        <div class="grow">
          <div class="inline">
            <div>‎</div>
            <div>{message}</div>
          </div>
          <hr />
        </div>
        <div class="br" />
        <Button fab size="small" active={isActive} on:click={() => alert(skull)}
          >⫸</Button
        >
      </div>
    </div>
  </Card>
  <div class="br" />
  <Card raised>
    <div class="padding">
      Genellikle yukarıdaki gibi DG kutlanıyor ama farklı bir şekilde kutlamak
      istedim.
    </div>
  </Card>
</div>
