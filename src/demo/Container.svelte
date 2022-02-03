<style>
    /* .container {
      background: #f5f5f5;
      position: fixed;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
    } */
    .container {
      background: #f5f5f5;
      height: 100%;
      /* overflow: auto; */
    }
  </style>
  
  <div class="scrollable container">
    <div style="margin: 24px;">
      <slot />
    </div>
  </div>