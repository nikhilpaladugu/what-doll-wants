<!-- App.svelte -->
<script>
    import { onMount } from 'svelte';
    import HoverImage from './HoverImage.svelte';

    // let images = Array(10).fill().map((_,i) => ({
    //   url: `images/bw/wdw_${i+1}.jpg`, // Using placeholder images for demo
    //   filename: `image_${i + 1}.jpg`,
    //   title: `Image ${i + 1}`,
    //   altImageUrl: `images/color/wdw_${i+1}.jpg`
    // }));
  
  </script>
  
  <main>
    
    <!-- spread 1 -->
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

    <!-- spread 2 -->
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

    <!-- spread 3 -->
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

    <!-- spread 4 -->
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

    <!-- spread 5 -->
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

    <!-- spread 6 -->
    <section>
      <div class="two-column">
        <div class="column">
          <div class="image-container">
            <img src="images/wdw_12.jpg" alt="">
          </div>
        </div>
        <div class="column">
          <div class="image-container">
            <img src="images/wdw_13.jpg" alt="">
          </div>
        </div>
      </div>
    </section>

    <!-- spread 7 -->
    <section>
      <div class="two-column">
        <div class="column">
          <div class="image-container">
            <HoverImage 
                defaultSrc="images/bw/wdw_10.jpg" 
                hoverSrc="images/color/wdw_10.jpg"
                alt="Image 1"
                alignment="right"
              />
          </div>
        </div>
        <div class="column">
          <div class="image-container">
            <HoverImage 
                defaultSrc="images/bw/wdw_11.jpg" 
                hoverSrc="images/color/wdw_11.jpg"
                alt="Image 1"
              />
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
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
        Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }

    :global(body) {
    background-color: #df348c; 
    }

    .section {
            /* height: 100vh; */
            width: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center; /* Center content vertically */
            align-items: center; /* Center content horizontally */
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

</style>