<template>
    <div>
        <div class="main-sidebar">
        <aside id="sidebar-wrapper">
          <div class="sidebar-brand">
            <nuxt-link to="/">My Admin</nuxt-link>
          </div>
          <div class="sidebar-brand sidebar-brand-sm">
            <nuxt-link to="/">MA</nuxt-link>
          </div>
          <ul class="sidebar-menu">
            <li v-for="(sidebar, i) in sidebars" :key="i">
              <nuxt-link class="nav-link" :to="sidebar.link">
                <i :class="sidebar.icon"></i>
                <span>{{sidebar.name}}</span>
              </nuxt-link>
            </li>
          </ul>
        </aside>
      </div>
    </div>
</template>
<script>
export default {
  props: {
    sidebars: {
      type: Array,
      default: () => []
    }
  }
}
</script>