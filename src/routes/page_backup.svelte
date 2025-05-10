<!-- App.svelte -->
<script>
    import { onMount } from 'svelte';
    
    // Sample data for 50 images (you would replace this with your actual data)
    let images = Array(29).fill().map((_, i) => ({
      id: i + 1,
      url: `images/wdw_${i+2}.jpg`, // Using placeholder images for demo
      filename: `image_${i + 1}.jpg`,
      title: `Image ${i + 1}`,
      altImageUrl: i == 28 ? `images/whatadollwants_finalselects_19.jpg` : null
    }));

    function hasAlternativeImage(filename) {
    // You can customize this condition based on your specific filename criteria
    // For example, checking if the filename contains a certain string or pattern
    return filename.includes('_29.jpg');
  }
  
  </script>
  
  
  <main>
    
    <div class="gallery">
      {#each images as image (image.id)}
        <div class="image-container">
          {#if hasAlternativeImage(image.filename) && image.altImageUrl}
          <div class="hover-image-wrapper">
            <img 
              src={image.url} 
              alt={image.title} 
              loading="lazy" 
              class="primary-image"
              on:mouseenter={(e) => {
                // Only change the image when hovering directly over it
                e.target.style.opacity = '0';
                e.target.nextElementSibling.style.opacity = '1';
              }}
              on:mouseleave={(e) => {
                // Reset when mouse leaves
                e.target.style.opacity = '1';
                e.target.nextElementSibling.style.opacity = '0';
              }}
            />
            <img 
              src={image.altImageUrl} 
              alt={`Alternative view of ${image.title}`} 
              loading="lazy" 
              class="hover-image"
            />
          </div>
        {:else}
          <img src={image.url} alt={image.title} loading="lazy" />
        {/if}
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

    .hover-image-wrapper {
    position: relative;
    width: 100%;
    overflow: hidden;
  }
  
  .primary-image,
  .hover-image {
    width: 100%;
    height: auto;
    display: block;
    object-fit: contain;
    max-height: 100vh;
    mix-blend-mode: multiply;
    /* transition: opacity 0.3s ease-in-out; */
  }
  
  .hover-image {
    position: absolute;
    top: 0;
    left: 0;
    opacity: 0;
    mix-blend-mode: normal;
    pointer-events: none;
  }
  

    
  img {
      width: 100%;
      height: auto;
      display: block;
      object-fit: contain;
      max-height: 100vh;
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