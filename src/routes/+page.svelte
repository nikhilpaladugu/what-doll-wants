<!-- App.svelte -->
<script>
    import { onMount } from 'svelte';
    
    // Sample data for 50 images (you would replace this with your actual data)
    let images = Array(28).fill().map((_, i) => ({
      id: i + 1,
      url: `images/wdw_${i+2}.jpg`, // Using placeholder images for demo
      title: `Image ${i + 1}`,
    }));
  
  </script>
  
  
  <main>
    
    <div class="gallery">
      {#each images as image (image.id)}
        <div class="image-container">
          <img src={image.url} alt={image.title} loading="lazy" />
        </div>
      {/each}
    </div>
  </main>
  
<style>
    main {
      max-width: 100%;
      /* margin: 0 auto;
      padding: 20px; */
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
        Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }

    :global(body) {
    background-color: #df348c; /* Light pink */
    /* margin: 0;
    padding: 0; */
    }
    
    .gallery {
      display: flex;
      flex-direction: column;
      max-width: 100%;
    }
    
    .image-container {
      width: 100%;
      overflow: hidden;
      /* margin: 0 auto; */
      background-color: transparent;
    }
    
    img {
      width: 100%;
      height: auto;
      display: block;
      object-fit: contain;
      /* max-height: 100vh;  */
      /* Limit height to 85% of viewport height */
      mix-blend-mode: multiply;
    }
    
    /* Basic responsive adjustments */
    /* @media (max-width: 768px) {
      .gallery {
        gap: 40px;
      }
    }
    
    @media (max-width: 480px) {
      .gallery {
        gap: 30px;
      }
    } */
</style>