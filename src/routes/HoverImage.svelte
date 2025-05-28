<script>
    import { tweened } from 'svelte/motion';
    import { cubicOut } from 'svelte/easing';

    // Props for the component
    export let defaultSrc = "";
    export let hoverSrc = "";
    export let alt = "";
    export let className = "";
    // export let defaultBlendMode = "multiply"; // Default to multiply
    // export let hoverBlendMode = "normal";     // Default to normal
    export let transitionDuration = 0; // Duration in ms, can be customized
    export let alignment = "left"; // Accepts "left", "center", or "right"
    export let imageOnlySpread = "false";
  
    // State to track if mouse is hovering
    let isHovering = false;

    // Create a tweened value for smooth transitions
    const hoverProgress = tweened(0, {
        duration: transitionDuration,
        easing: cubicOut
    });
  
    // Update the tweened value when hover state changes
    $: {
        if (isHovering) {
        hoverProgress.set(1);
        } else {
        hoverProgress.set(0);
        }
    }
  
    // Calculate the current blend mode based on the progress
    // $: blendMode = $hoverProgress > 0.5 ? hoverBlendMode : defaultBlendMode;
    
    $: alignmentClass = `align-${alignment}`;

    $: imageOnlySpread = `padding-${imageOnlySpread}`;
  </script>

    <div 
    class="hover-image-container {className}{alignmentClass}"
    on:mouseenter={() => isHovering = true}
    on:mouseleave={() => isHovering = false}
    >
    <!-- Default image (visible when not hovering) -->
    <img 
    src={defaultSrc}
    {alt}
    class="image default-image"
    style="opacity: {1 - $hoverProgress};"
    />

    <!-- Hover image (visible when hovering) -->
    <img 
    src={hoverSrc}
    {alt}
    class="image hover-image"
    style="opacity: {$hoverProgress};"
    />
    </div>

    <!-- style="opacity: {1 - $hoverProgress}; mix-blend-mode: {blendMode};" -->
    <!-- style="opacity: {$hoverProgress}; mix-blend-mode: {blendMode};" -->
    <style>
        .hover-image-container {
          position: relative;
          display: inline-block;
          overflow: hidden;
          margin-left: auto;
          margin-right: 0;
        }

        .align-left{
          margin-left: 0;
          margin-right: auto;
        }
        
        .align-center {
            margin-left: auto;
            margin-right: auto;
        }
        
        .align-right {
            margin-left: auto;
            margin-right: 0;
        }
        
        .image {
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          object-fit: cover;
          /* transition: mix-blend-mode 0.15s ease; */
        }
        
        .default-image {
          position: relative; /* Not absolute so it sets the container dimensions */
        }

        .padding-false {
          padding: 0%;
        }

        .padding-true {
          padding: 10%;
        }
      </style>