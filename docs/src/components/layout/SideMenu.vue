<template>
  <div
    :class="`sidebar ${showDrawer ? 'show-drawer' : ''}`"
    @click="$emit('toggle-drawer')"
  >
    <div class="nav-list">
      <div class="sidebar__logo" @click="$router.push('/')">
        <img src="@/assets/logo.svg" class="header-logo" />
        <h3>&nbsp; PLUG-UI</h3>
      </div>
      <nuxt-link to="/" class="nav-item">
        <div class="nav-label">Getting Started</div>
      </nuxt-link>
      <!-- <div class="nav-item">
        <div class="nav-label">Source Code</div>
      </div>
      <div class="nav-item">
        <div class="nav-label">Support</div>
      </div> -->

      <nuxt-link to="/flexbox" class="nav-item">
        <div class="nav-label">Flexbox</div>
      </nuxt-link>
      <nuxt-link to="/css-grid" class="nav-item">
        <div class="nav-label">CSS Grid</div>
      </nuxt-link>
      <nuxt-link to="/shadows" class="nav-item">
        <div class="nav-label">Box Shadows</div>
      </nuxt-link>
      <nuxt-link to="/buttons" class="nav-item">
        <div class="nav-label">Buttons</div>
      </nuxt-link>
      <nuxt-link to="/alerts" class="nav-item">
        <div class="nav-label">Inline Alerts</div>
      </nuxt-link>
      <nuxt-link to="/responsive-area" class="nav-item">
        <div class="nav-label">Responsive Area</div>
      </nuxt-link>
        <nuxt-link to="/dropdown" class="nav-item">
        <div class="nav-label">CSS Dropdown</div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  props: ["showDrawer"],
  methods: {},
};
</script>

<style scoped lang="scss">
.sidebar {
  position: fixed;
  left: 0;
  top: 55px;
  height: calc(100% - 55px);
  background-color: #ffffff;
  overflow: auto;
  width: 250px;
  // border-right: 1px solid #dee2e6;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-transition: -webkit-transform 0.4s cubic-bezier(0.05, 0.74, 0.2, 0.99);
  transition: -webkit-transform 0.4s cubic-bezier(0.05, 0.74, 0.2, 0.99);
  transition: transform 0.4s cubic-bezier(0.05, 0.74, 0.2, 0.99);
  transition: transform 0.4s cubic-bezier(0.05, 0.74, 0.2, 0.99),
    -webkit-transform 0.4s cubic-bezier(0.05, 0.74, 0.2, 0.99);

  box-shadow: 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 2px 2px 0 rgba(0, 0, 0, 0.14),
    0 1px 5px 0 rgba(0, 0, 0, 0.12);
}

.nav-item {
  color: #566d79;
  display: block;
  padding: 12px 16px;
  // border-radius: 3px;
  cursor: pointer;
  font-size: 14px;
}
.nav-item.active,
.nav-item:hover {
  background-color: #f1f5f8;
}
.nav-list {
  padding: 20px 0px;
  .nuxt-link-exact-active {
    background-color: #e0e7ec;
  }
}
.nav-label {
  margin-left: 12px;
}
.sidebar__logo {
  display: none;
  align-items: center;
  cursor: pointer;
  margin: 0px 0px 20px 20px;
  .header-logo {
    width: 80px;
  }
}
@media (max-width: 768px) {
  .sidebar {
    height: 100%;
    top: 0px;
    z-index: 999;
    transform: translateX(-100%);
    transition: all 0.3s ease-in-out;
  }
  .sidebar.show-drawer {
    transform: translateX(0px);
  }
  .menu-icon {
    display: none;
  }
  .sidebar__logo {
    display: flex;
  }
}
</style>
