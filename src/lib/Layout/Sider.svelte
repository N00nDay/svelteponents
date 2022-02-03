<script>
    // import { afterUpdate } from "svelte";
    import addStyle from "../../utilities/addStyle";
    export let theme = "light";
    export let style = undefined;
    export let collapsed = false;
    export let width = 200;
    export let collapsedWidth = 80;
  
    // afterUpdate(async () => {
    //   if (collapsed) {
    //     style = addStyle({
    //       style,
    //       attribute: true,
    //       string: `width: ${collapsedWidth}px;`
    //     });
    //   } else {
    //     style = addStyle({
    //       style,
    //       attribute: true,
    //       string: `width: ${width}px;`
    //     });
    //   }
    // });

    addStyle({
      style,
      attribute: true,
    });
  </script>
  
  <style>
    .sider {
      position: relative;
      /* fix firefox can't set width smaller than content on flex item */
      min-width: 0;
      background: #001529;
      -webkit-transition: all 0.2s;
      transition: all 0.2s;
      width: var(--width);
    }
    .sider-children {
      height: 100%;
      margin-top: -0.1px;
      padding-top: 0.1px;
    }
    /* .sider-zero-width > * {
      overflow: hidden;
    } */
    .sider-light {
      background: #fff;
    }
  </style>
  
  <aside
    class="sider scrollable"
    class:sider-light={theme === 'light'}
    class:sider-dark={theme === 'dark'}
    class:collapsed
    style={`${style ? style : ""}--width:${collapsed ? `${collapsedWidth}px` : `${width}px`}`}>
    <div class="sider-children">
      <slot />
    </div>
  </aside>