<!-- App.svelte -->
<script>
    import { onMount } from 'svelte';
    import HoverImage from './HoverImage.svelte';

    let images = Array(10).fill().map((_,i) => ({
      url: `images/bw/wdw_${i+1}.jpg`, // Using placeholder images for demo
      filename: `image_${i + 1}.jpg`,
      title: `Image ${i + 1}`,
      altImageUrl: `images/color/wdw_${i+1}.jpg`
    }));

    function hasAlternativeImage(filename) {
    // You can customize this condition based on your specific filename criteria
    // For example, checking if the filename contains a certain string or pattern
    return filename.includes('_29.jpg');
  }

  // Track which image is currently being hovered (if any)
  let hoveredId = null;
  
  // Mouse enter handler
  function handleMouseEnter(id) {
    hoveredId = id;
  }
  
  // Mouse leave handler
  function handleMouseLeave() {
    hoveredId = null;
  }

  
  </script>
  
  <main>
    
    <!-- <div class="gallery">
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
    </div> -->

    <section class="section">
      <div class="two-column">
        <div class="column">
          <div class="split-vertical">
            <div class="image-box">
              <div class="image-container">
              <HoverImage 
                defaultSrc="images/bw/wdw_1.jpg" 
                hoverSrc="images/color/wdw_1.jpg"
                alt="Image 1" 
                alignment="right"
              />
              </div>
            </div>
            <div class="image-box">
              <div class="image-container">
                <HoverImage 
                defaultSrc="images/bw/wdw_2.jpg" 
                hoverSrc="images/color/wdw_2.jpg"
                alt="Image 1" 
                alignment="right"
              />
              </div>
            </div>
          </div>
        </div>
        <div class="column">
          <div class="image-container">
            <img src="images/wdw_3.jpg" alt="" class="left-img-50"/>
          </div>
        </div>
      </div>
    </section>

    <section>
              <div class="image-container-full-spread">
                <HoverImage 
                defaultSrc="images/bw/wdw_3.jpg" 
                hoverSrc="images/color/wdw_3.jpg"
                alt="Image 1"
                alignment="center"
                />
              </div>
    </section>

    <section>
      <div class="two-column">
        <div class="column">
          <div class="image-container">
            <img src="images/wdw_5.jpg" alt="">
          </div>
        </div>
      <div class="column">
        <div class="split-vertical">
          <div class="image-box">
            <div class="image-container">
              <img src="images/wdw_6.jpg" alt=""/>
            </div>
          </div>
          <div class="image-box">
            <div class="image-container">
              <HoverImage 
                defaultSrc="images/bw/wdw_4.jpg" 
                hoverSrc="images/color/wdw_4.jpg"
                alt="Image 1"
              />
            </div>
          </div>
        </div>
      </div>
      </div>
    </section>

    <section>
      <div class="two-column">
        <div class="column">
          <div class="image-container">
            <img src="images/wdw_8.jpg" alt="">
          </div>
        </div>
      <div class="column">
        <div class="split-vertical">
          <div class="image-box-2">
            <div class="image-container">
              <HoverImage 
                defaultSrc="images/bw/wdw_5.jpg" 
                hoverSrc="images/color/wdw_5.jpg"
                alt="Image 1"
              />
            </div>
          </div>
          <div class="image-box-3">
            <div class="image-container">
              <img src="images/wdw_10.jpg" alt=""/>
            </div>
          </div>
        </div>
      </div>
      </div>
    </section>

    <section>
      <div class="two-column">
        <div class="column">
          <div class="split-vertical">
            <div class="image-box">
              <div class="image-container">
                <HoverImage 
                defaultSrc="images/bw/wdw_6.jpg" 
                hoverSrc="images/color/wdw_6.jpg"
                alt="Image 1"
                alignment="right"
                />
              </div>
            </div>
            <div class="image-box">
              <div class="image-container">
                <HoverImage 
                defaultSrc="images/bw/wdw_7.jpg" 
                hoverSrc="images/color/wdw_7.jpg"
                alt="Image 1"
                alignment="right"
                />
              </div>
            </div>
          </div>
        </div>
      <div class="column">
        <div class="split-vertical">
          <div class="image-box">
            <div class="image-container">
              <HoverImage 
                defaultSrc="images/bw/wdw_8.jpg" 
                hoverSrc="images/color/wdw_8.jpg"
                alt="Image 1"
              />
            </div>
          </div>
          <div class="image-box">
            <div class="image-container">
              <HoverImage 
                defaultSrc="images/bw/wdw_9.jpg" 
                hoverSrc="images/color/wdw_9.jpg"
                alt="Image 1"
              />
            </div>
          </div>
        </div>
      </div>
      </div>
    </section>
  </main>
  
<style>
    main {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
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

    #color{
      display: none;
    }

    #replace{
      align-items: center;
      justify-content: center;
    }

    .section {
            /* height: 100vh; */
            width: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center; /* Center content vertically */
            align-items: center; /* Center content horizontally */
            scroll-snap-align: start;
            padding: 0;
            position: relative;
            box-sizing: border-box;
            overflow: hidden;
    }

    .two-column {
            display: flex;
            width: 100%;
            height: 90vh;
            margin: 0;
            box-sizing: border-box;
    }

    .column {
            width: 50%;
            padding: 15px;
            /* border: 2px solid lime; */
            box-sizing: border-box;
    }

    .image-container {
            width: 100%;
            height: 80vh; /* Takes most of the section height */
            overflow: hidden;
            margin-bottom: 0;
            /* border: 2px solid blue; */
            display: flex;
    }

    .image-container-full-spread {
            width: 100%;
            height: 80vh; /* Takes most of the section height */
            overflow: hidden;
            margin-bottom: 0;
            /* border: 2px solid blue; */
            display: flex;
    }

    .image-container-full-spread img{
            width: 100%;
            height: 100%;
            object-fit: contain; /* Ensures image fits completely within container */
            transition: transform 0.5s;
            padding: 20px;
    }

    .image-container img {
            width: auto;
            height: 100%;
            object-fit: contain; /* Ensures image fits completely within container */
            /* border: 2px solid rgb(217, 0, 255); */
    }

    .column:first-child .image-container img{
          /* object-position: right; */
          margin-left: auto;
          margin-right: 0;
        }

        .column:first-child .image-container .photo{
          /* object-position: right; */
          margin-left: auto;
          margin-right: 0;
        }

        /* .column:last-child .image-container img{
          object-position: left;

        } */

        /* .split-vertical .image-box .image-container img{
          object-position: right;

        } */

    .split-vertical {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 80vh;
            gap: 20px; /* Gap between images */
    }

    .image-box {
            width: 100%;
            height: calc(40vh - 20px);
    }

    .image-box-2 {
            width: 100%;
            height: calc(65vh - 20px);
    }

    .image-box-2 .image-container {
            height: 100%;
            margin-bottom: 0;
    }

    .image-box-3 {
            width: 100%;
            height: calc(15vh - 20px);
    }

    .image-box-3 .image-container {
            height: 100%;
            margin-bottom: 0;
    }
        
    .image-box .image-container {
            height: 100%;
            margin-bottom: 0;
    }

    img{
      mix-blend-mode: multiply;
    }

    .image-container-full-spread:hover #bw{
      display: none;
    }

    .image-container-full-spread:hover #color{
      display: block;
      mix-blend-mode: normal;
    }

    /* .image-container {
      width: 100%;
      overflow: hidden;
      /* margin: 0 auto;
      background-color: transparent;
    } */

    .hover-image-wrapper {
    position: relative;
    width: 100%;
    overflow: hidden;
  }

  

    
  /* img {
      width: 100%;
      height: auto;
      display: block;
      object-fit: contain;
      max-height: 100vh;
      /* Limit height to 85% of viewport height
      mix-blend-mode: multiply;
  } */
    
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