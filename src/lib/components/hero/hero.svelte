<script>
</script>

<section class="hero">
  <h1>
    Als lid van de <span class="accent">OBA</span> krijg je toegang tot onze collectie, korting op
    evenementen en een heleboel andere voordelen.
  </h1>
  <div class="gradient">
    <img
      class="hero-img"
      src="https://oba.nl/_next/image?url=https%3A%2F%2Fcdn-assets-dynamic.frontify.com%2F4001580%2FeyJhc3NldF9pZCI6NDQyMH0%3Athe-oba%3A_HFLFCPYXtzP_dC_HVNBpQrl-rBpI7upFNHxhteZ-1M&w=1080&q=75"
    />
  </div>
</section>

<style>
  .hero {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: end;
    height: 70vh;


    & h1{
        z-index: 1;
        padding: 1.5rem 2rem;
        color: white;
    }
  }

  .gradient{
    position: absolute;
    top: 0;
    height: 100%;
    width: 100%;
    background: linear-gradient( #33333324, #33333384 50%, #3c3c3cd7 70%, #262525d0 100%);
        border-radius: 0.5rem;
  }

  .hero-img{
    position: absolute;
    top: 0;
    height: 100%;
    width: 100%;
    object-fit: cover;
    z-index: -1;
    border-radius: 0.5rem;
  }
</style>
