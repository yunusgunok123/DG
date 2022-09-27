<script lang="ts">
  import { Button, Card } from "svelte-materialify";
  let showPoem = false;
</script>

<div class="main">
  <Card raised>
    <div class="padding">
      {#if showPoem}
        <h6 class="text-h6">Memento Mori</h6>
        <div class="br" />
        <hr />
        <div class="br" />
        <div class="br" />
        <div>İnsan meyveyi yediği an kaderini mühürledi.</div>
        <div>Belki kara ve sönük bir umuda sarılıyor.</div>
        <div>
          Yine de oluşturduğu ilişkiler, yolun aydınlanmasını sağlayacak.
        </div>
        <div class="br" />
        <div class="br" />
        <div>Gidilen yolun sonunda onun mutlak sonu var.</div>
        <div>Kim olduğu önemli değil.</div>
        <div>
          Yine de oluşturduğu ilişkiler, yolun devam etmesini sağlayacak.
        </div>
        <div class="br" />
        <div class="br" />
        <div>Ancak o zaman gezginin hikayesi yaşayacak,</div>
        <div>Ona veda eden ve sevenler tarafından.</div>
      {:else}
        <div>
          Bu projeyi insanları belki istemese de mutlu etme düşüncesi ile
          hazırladım ve umarım proje sende amacına ulaşmıştır.
        </div>
        <div class="br" />
        <div>
          Lütfen bunu başkaları ile paylaşma, onlara da sürpriz olmasını
          istiyorum. Yani bu proje için az zaman harcamadım.
        </div>
        <div class="br" />
        <div class="green-text">
          // Merak etme bide virüs filan yok ya da var mı?
        </div>
      {/if}
    </div>
  </Card>
  {#if !showPoem}
    <div class="br" />
    <Card raised>
      <div class="padding">
        <div>
          Şimdi sona yazdığım minik bir şiiri ekledim ama ben yazmakta yetenekli
          (ya da özgüvenli) değilimdir.
        </div>
        <div class="br" />
        <Button
          outlined
          block
          class="red-text"
          on:click={() => (showPoem = true)}>Oku 😓</Button
        >
      </div>
    </Card>
  {/if}
</div>
