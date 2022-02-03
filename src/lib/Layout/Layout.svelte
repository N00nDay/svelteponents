<script>
    export let style = undefined;
  </script>
  
  <style>
    .layout {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-flex: 1;
      -ms-flex: auto;
      flex: auto;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      /* fix firefox can't set height smaller than content on flex item */
      min-height: 0;
      background: #f0f2f5;
      height: 100%;
    }
    .layout,
    .layout * {
      -webkit-box-sizing: border-box;
      box-sizing: border-box;
      overflow: hidden;
    }
    .layout.has-sider {
      -webkit-box-orient: horizontal;
      -webkit-box-direction: normal;
      -ms-flex-direction: row;
      flex-direction: row;
    }
    .layout.has-sider > :global(.layout),
    .layout.has-sider > :global(.content) {
      overflow-x: hidden;
    }
  </style>
  
  <section class="layout" class:has-sider={$$slots['outer-sider-left'] || $$slots['inner-sider-left'] || $$slots['inner-sider-right']} {style}>
    <slot name="outer-sider-left" />
    <slot name="header" />
    <slot name="inner-layout" />
    <slot name="inner-sider-left" />
    <slot name="content" />
    <slot name="inner-sider-right" />
    <slot name="footer" />
  </section>