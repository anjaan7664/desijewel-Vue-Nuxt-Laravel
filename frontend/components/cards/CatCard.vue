<template>
  <div
    class="bg-gray-100 shadow-neumorph
    relative flex flex-col transition-all duration-300 m-2 md:m-4
    rounded-2xl transform md:hover:-translate-y-3"
  >
    <div class="relative pb-1/1">
      <img
      loading="lazy"
        :src="require('/assets/img/icons/' + catData.image)"
        :alt="$t(catData.name)+' icon'"
        class="shadowed absolute p-2 mx-auto w-full h-full object-contain"
      />
    </div>
    <div
      class="text-black  font-semibold text-2xl md:text-xl lg:text-2xl mt-auto py-2"
    >
      <h2>{{ $t(catData.name) }}</h2>
    </div>
  </div>
</template>
<script>
export default {
  name: "CatCard",
  props: ["catData"]
};
</script>
<style lang="scss">
.shadowed {
  filter: drop-shadow(5px 25px 15px rgba(0, 0, 0, 0.3));
}

</style>
