<template>
  <div class="relative designComponent">
    <div
      class="relative flex flex-col overflow-hidden transition duration-150
       bg-white rounded rounded-t rounded-b-none group"
      style="box-shadow:8px 12px 16px 0 rgba(0, 0, 0, 0.25),-6px -6px 25px 0 rgba(222, 47, 69, 0.1)"
    >
      <div class="relative md:pb-4/6">
        <nuxt-link
          :to="
            localePath({
              path:'/'+catMetal+'/design/' + (((designData.title) == '') ? designData.image : designData.title),
              query: { subCat: designData.sub_category }
            })
          "
        >
          <img
            loading="lazy"
            :src="currentImage"
            :alt="designAlt"
            class="lazy-img-fadein md:absolute h-full w-full object-cover rounded min-h-[16rem]
           transition duration-300 ease-in-out transform"
          />
        </nuxt-link>
      </div>
    </div>
    <div
      class="relative py-2 mt-auto text-2xl font-semibold text-black md:text-xl lg:text-2xl"
    >
      <ul class="inline-block mb-4 text-xl text-left">
        <li v-show="designData.weight" class="">
          <!-- <span class="font-bold">Price - </span><span>150000</span> -->
          <span class="font-bold">Weight </span
          ><span ref="designWeight">{{ designData.weight }}</span>
        </li>
      </ul>
      <p class="text-sm" v-if="adminAccess">{{designData.comment}}</p>
      <p class="absolute top-0 text-xl">
        <nuxt-link
          :to="
            localePath({
              path: '/gold/' + designData.category,
              query: { subCat: designData.sub_category }
            })
          "
          class="text-blue-400 underline capitalize"
        >
          <span >{{ designData.sub_category }}</span>
        </nuxt-link>
      </p>
      <p  v-if="$auth.loggedIn && !$auth.user.role.includes('user') " class="absolute top-0 right-0 text-xl">
        <span ref="designHit"> likes - {{ designData.hit }}</span>
      </p>
    </div>
    <AdminEdit
       v-if="$auth.loggedIn && !$auth.user.role.includes('user') "
      :designData="designData"
      @updateWeight="updateWeight"
      @updateHit="updateHit"
      @removeDesign="removeDesign"
    />
  </div>
</template>
<script>
export default {
  name: "DesignCard",
  props: ["designData","catMetal","adminAccess"],
  data() {
    return {
      currentImage:
        "/designs/thumb/" +
        [
          this.designData.path +
            this.designData.image +
            "." +
            this.designData.img_type
        ],
    };
  },
  computed: {
    designAlt() {
      if(this.$i18n.locale == "en"){
        return this.designData.alt;
      }
      return this.designData.alt_hn;
    }
  },
  methods: {
    updateWeight: function(e) {
      this.$refs.designWeight.innerText = e;
    },
    updateHit: function(e) {
         this.$refs.designHit.innerText = e;
    },
    removeDesign: function(e) {
      if (e == true) {
        document
          .getElementsByClassName("designComponent")
          .classList.add("hidden");
      }
    }
  }
};
</script>
<style lang="scss">
.group:hover div img {
  @apply md:scale-110 md:-translate-y-1;
}
.group:hover div div {
  @apply opacity-100;
}
</style>
