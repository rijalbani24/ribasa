<template>
  <div
    class="bg-[url('/4907151.jpg')] bg-cover bg-center bg-no-repeat py-10 lg:py-20"
  >
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 place-items-center px-4">
      <div class="animate-fadeUpLoop">
        <img src="/ribasa-home2.png" class="w-200" alt="" />
      </div>
      <div class="text-center">
        <div class="text-2xl text-[#ffed31] font-bold">
          Creating Digital Experiences
        </div>
        <div class="text-2xl text-[#ffed31] font-bold mb-5">
          Through Completed Projects
        </div>
        <div class="text-[15px] text-[#ffed31] font-semibold">
          RIBASA.WEB.ID merupakan sebuah portofolio digital yang menampilkan
          berbagai proyek dan hasil pekerjaan yang telah dikembangkan secara
          profesional, sebagai representasi kemampuan dalam bidang pengembangan
          teknologi dan layanan berbasis web.
        </div>
        <div class="mt-5">
          <NuxtLink
            class="bg-[#7b5cff] text-white hover:text-black p-2 inline-block rounded-md shadow-2xl font-semibold hover:bg-[#ffed31]"
            to="#about"
          >
            Read More
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>

  <div id="about" class="grid grid-cols-1 lg:grid-cols-2 bg-black">
    <UContainer>
      <div class="mb-10">
        <div
          class="text-2xl font-bold text-center text-[#ffed31] my-5 underline underline-offset-4"
        >
          About Me
        </div>
        <div class="mt-2 text-white leading-relaxed">
          Portofolio ini saya buat sebagai wadah untuk menampilkan beberapa
          proyek digital yang pernah saya kerjakan dan kembangkan sejauh ini.
          Setiap karya di sini menjadi bagian dari proses belajar dan eksplorasi
          saya dalam memahami bagaimana desain dan pengembangan dapat berjalan
          seimbang antara fungsi dan tampilan.
        </div>
        <div class="mt-2 text-white leading-relaxed">
          Saya percaya bahwa setiap proyek memiliki proses dan pembelajaran
          tersendiri. Dengan berusaha memahami kebutuhan setiap ide dan
          memperhatikan detailnya, saya terus mencoba menghasilkan karya yang
          sederhana namun tetap bermakna. Portofolio ini menjadi catatan
          perjalanan saya dalam mengembangkan diri di dunia digital.
        </div>
      </div>
    </UContainer>
    <UContainer>
      <div class="flex justify-center mb-20">
        <img
          src="/19362653.png"
          alt="Illustration"
          class="max-w-sm w-full rounded-2xl shadow-lg animate-zoomInOut"
        />
      </div>
    </UContainer>
  </div>

  <div class="bg-[#16171d] py-10">
    <UContainer class="my-10">
      <div class="text-2xl mb-10 text-white text-center font-bold underline underline-offset-8">
        Learning and Building with Modern Tools
      </div>
      <div class="text-white text-center">
        Berbagai tools dan teknologi telah saya gunakan selama proses belajar dan pengembangan, mulai dari proyek sederhana hingga sistem yang lebih terstruktur. Pengalaman tersebut membantu saya memahami alur kerja yang efisien dan mudah dikembangkan.
      </div>
      <div class="mt-5">
        <UCarousel
          v-slot="{ item }"
          loop
          :autoplay="{ delay: 2000 }"
          :items="items"
          :ui="{ item: 'basis-1/3' }"
        >
          <div class="flex flex-col items-center">
            <img :src="(item as any).image" width="150" height="150" class="rounded-lg hover:scale-115" />
            <p class="mt-2 font-semibold text-white">{{ (item as any).title }}</p>
          </div>
        </UCarousel>
      </div>
    </UContainer>
  </div>

  <section class="bg-black text-white py-16 text-center">
  <h2 class="text-3xl font-bold mb-6 underline underline-offset-8">My Projects</h2>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8 px-6">
    <!-- Card Project -->
    <div class="bg-gray-800 rounded-2xl p-4 shadow-lg hover:scale-105 transition">
      <img src="/portofolio1.png" alt="Project 1" class="rounded-lg mb-4">
      <h3 class="text-xl font-semibold">Web Company Profile</h3>
      <p class="text-sm mt-2 text-gray-300">Website company profile yang menampilkan informasi perusahaan secara profesional, dibangun menggunakan framework Laravel dan template Bootstrap untuk tampilan yang responsif dan modern.</p>
      <a href="https://ingriagroup.com/id" target="_blank"
        class="mt-4 inline-block text-blue-400 hover:text-blue-500 underline underline-offset-4 transition">
        View
      </a>
    </div>
    <div class="bg-gray-800 rounded-2xl p-4 shadow-lg hover:scale-105 transition">
      <img src="/monas.png" alt="Project 2" class="rounded-lg mb-4">
      <h3 class="text-xl font-semibold">Web Company Profile</h3>
      <p class="text-sm mt-2 text-gray-300">Website company profile yang menampilkan informasi perusahaan secara profesional, dibuat menggunakan Laravel dan Nuxt.js untuk tampilan yang responsif dan mudah dikembangkan.</p>
      <a href="https://monas-three.vercel.app/" target="_blank"
        class="mt-4 inline-block text-blue-400 hover:text-blue-500 underline underline-offset-4 transition">
        View
      </a>
    </div>
    <div class="bg-gray-800 rounded-2xl p-4 shadow-lg hover:scale-105 transition">
      <img src="/landingpage.png" alt="Project 1" class="rounded-lg mb-4">
      <h3 class="text-xl font-semibold">Web Landing Page</h3>
      <p class="text-sm mt-2 text-gray-300">Website landing page yang dibuat menggunakan WordPress dan plugin Elementor, dengan desain responsif dan mudah disesuaikan.</p>
      <a href="https://griaindahcibarusah.com/" target="_blank"
        class="mt-4 inline-block text-blue-400 hover:text-blue-500 underline underline-offset-4 transition">
        View
      </a>
    </div>

  </div>
  <NuxtLink
    class="bg-[#7b5cff] mt-5 text-white hover:text-black p-2 inline-block rounded-md shadow-2xl font-semibold hover:bg-[#ffed31]"
    to="/project"
  >
    More Projects
  </NuxtLink>
</section>

<div class="text-center py-10 bg-[#16171d] text-gray-400 italic leading-relaxed">
  “Belajar, mencoba, dan terus berkembang —<br>
  karena setiap baris kode membawa saya lebih dekat ke hasil yang lebih baik.”
</div>

</template>

<script lang="ts" setup>
  
  const items = [
  { image: 'laravel3.png', title: 'Laravel' },
  { image: 'vue.png', title: 'Vue.js' },
  { image: 'nuxt.png', title: 'nuxt.js' },
  { image: 'tailwindcss.png', title: 'Tailwind CSS' },
  { image: 'bootstrap.png', title: 'Bootstrap' },
  { image: 'wordpress.png', title: 'wordpress' }
]

</script>
<style>
@keyframes fadeUpLoop {
  0%,
  100% {
    opacity: 1;
    transform: translateY(20px);
  }
  50% {
    opacity: 1;
    transform: translateY(0);
  }
}
.animate-fadeUpLoop {
  animation: fadeUpLoop 3s ease-in-out infinite;
}
.delay-300 {
  animation-delay: 0.3s;
}

@keyframes zoomInOut {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.08);
  }
}

.animate-zoomInOut {
  animation: zoomInOut 6s ease-in-out infinite;
}

html {
  scroll-behavior: smooth;
}
</style>


