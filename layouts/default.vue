<template>
  <div class="main-wrapper">
      <navbar />
      <sidebar :sidebars="sidebars" />

      <!-- Main Content -->
      <div class="main-content">
        <section class="section">
          <div class="section-body">
            <Nuxt />
          </div>
        </section>
      </div>
      <footer-stisla />
    </div>
</template>

<script>
export default {
  data() {
    return {
      sidebars: [
        {
          name: "Dashboard",
          link: "/",
          icon: "fas fa-tachometer-alt"
        },
        {
          name: "Increment",
          link: "/increment",
          icon: "fas fa-fire"
        },
        {
          name: "Student",
          link: "/student",
          icon: "fas fa-users"
        },
        {
          name: "Book",
          link: "/book",
          icon: "fas fa-book"
        },
        {
          name: "Reader",
          link: "/reader",
          icon: "fas fa-users"
        }
      ]
    }
  }
}
</script>
