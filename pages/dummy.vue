<template>
  <div>
    <nuxt-link to="/">Home</nuxt-link>
    <nuxt-link to="/">Dummy</nuxt-link>
    <div>Dummy page</div>
  </div>
</template>

<script>
export default {
  middleware({ route, redirect }) {
    console.log(process.static);
    if (process.static) {
      return;
    }

    if (route.path.includes("dummy")) {
      return redirect("/");
    }
  }
};
</script>
