<template>
  <div>
    <section class="w-full text-center my-4">
      <h1 class="px-1 my-4 hmain ">Download Our App</h1>
      <div class="flex flex-col w-full md:flex-row">
        <div class="text-center md:w-1/2">
          <div class="px-3 mt-8 text-center">
            <img
              src="~/assets/img/app_ss.webp"
              alt="Desi Jewellery App"
              class="mx-auto rounded shadow-lg2 md:w-3/4 min-h-[16rem]"
            />
          </div>
        </div>
        <div class="text-center md:w-1/2 md:text-left">
          <div class="mx-3 md:mx-8 mt-6">
            <p class="text-lg text-left md:text-xl ">
              We have many user who are not greatly familiar with browser and couldn't access our website.
              For their convenience we have made an android app for them. With this App user can easily access our design.
              You can download this app from Play store via clicking on below link
            </p>
            <a
              href="https://play.google.com/store/apps/details?id=satlaa.desijewellery"
              target="_blank"
              class=""
              rel="external"
            >
              <img
                src="~/assets/img/play_store.webp"
                class="w-2/3 md:w-1/2 mt-4"
                alt="Donwnload Desi Jewellery on Play Store"
            /></a>
          </div>
        </div>
      </div>
    </section>
    <!-- About Us  -->
    <!-- <section class="flex flex-col my-6 md:flex-row">
      <div class="text-left text-center md:full">
        <h1 class="mt-12 hmain md:mt-auto md:my-4">About Us</h1>
        <div class="mt-6">
          <p class="mx-8 text-lg text-left md:text-2xl">
            We are making gold jewellery for past many generations.
          </p>
        </div>
      </div>
    </section> -->
  </div>
</template>
<script>
export default {
  name: "extras"
};
</script>
