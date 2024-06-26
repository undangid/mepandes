<script setup>
import { onMounted, ref } from 'vue';
import AOS from 'aos';
import { ArrowDownIcon, MapPinIcon } from '@heroicons/vue/20/solid';
import InvitationPopup from './components/InvitationPopup.vue';

onMounted(() => {
  AOS.init();
});

const params = new URLSearchParams(window.location.search);
const invitee = params.get('to');

const backsound = ref(null);

const isPopupShown = ref(true);
const hidePopup = () => {
  document.body.classList.remove('overflow-hidden');

  if (backsound.value) {
    backsound.value.play();
  }

  isPopupShown.value = false;
}

const openMap = () => {
  window.open('https://maps.app.goo.gl/spctNu1J8w7618X4A?g_st=iw');
}
</script>

<template>
  <audio src="https://swalapatra.com/wp-content/uploads/2023/03/y2mate.com-INSTRUMEN-RATU-ANOM-LAGU-BALI.mp3"
    class="hidden" ref="backsound"></audio>
  <Transition>
    <InvitationPopup :invitee="invitee" v-show="isPopupShown" @hide-popup="hidePopup" />
  </Transition>
  <div class="section flex flex-col items-center text-center justify-center gap-8 px-4">
    <img src="./assets/leaf.png" class="h-10 mt-4 rotate-180">
    <div data-aos="fade-up" data-aos-delay="100">
      <p class="text-xl">Upacara Manusa Yadnya</p>
      <h1 class="text-4xl font-dancing-script">Mepandes / Potong Gigi</h1>
    </div>
    <div data-aos="fade-up" data-aos-delay="200">
      <p>
        "Jitatmanah prasantasya pramatma samahita,
        sitosna-sukha-duhkhesu tatha manapamanayoh."
      </p>
    </div>
    <div data-aos="fade-up" data-aos-delay="200" class="flex flex-col items-center">
      <p class="underline">
        Tuhan dengan teguh berada pada hati dia yang bisa
        mengendalikan diri, damai dan berada di atas dari
        sepasang hal yang bertentangan, seperti panas dan
        dingin, pujian dan hinaan.
      </p>
      <img src="./assets/leaf.png" class="h-10 mt-4">
    </div>
    <ArrowDownIcon class="h-10 text-indigo-600 animate-bounce" />
  </div>
  <div class="section px-4" style="height: 100%;">
    <div class="overflow-hidden rounded-lg bg-white shadow">
      <div class="px-4 py-8 sm:p-6 text-center flex flex-col text-indigo-900" data-aos="fade-up" data-aos-delay="100">
        <div class="font-dancing-script text-2xl flex flex-col gap-y-2">
          <p>Ida Bagus Gede Sindhu</p>
          <p>Ida Ayu Made Sintya Maha Dewi</p>
        </div>
        <p class="my-8 font-semibold tracking-widest uppercase">Putra dan Putri dari pasangan</p>
        <div class="font-dancing-script text-2xl">
          <p>Ida Bagus Gede Wisnawa, S.Pd.B</p>
          <p>&</p>
          <p>Ida Ayu Alit Rustini</p>
        </div>
        <img src="./assets/leaf.png" class="h-10 mt-4 self-center">
      </div>
    </div>

    <div class="flex justify-end my-16" data-aos="fade-up" data-aos-delay="200">
      <ArrowDownIcon class="h-10 text-indigo-600 animate-bounce" />
    </div>

    <div class="overflow-hidden rounded-lg bg-white shadow my-20">
      <div class="px-4 py-8 sm:p-6 text-center flex flex-col text-indigo-900">
        <div class="flex flex-col gap-y-2" data-aos="fade-up" data-aos-delay="100">
          <h1 class="font-dancing-script text-4xl">Om Swastiastu,</h1>
          <p class="mt-4">Atas Asung Kertha Wara Nugraha Ida Sang Hyang Widhi Wasa/ Tuhan Yang Maha Esa, kami bermaksud
            mengundang
            Bapak/ Ibu/ Saudara/ i pada</p>
          <p class="font-bold">UPACARA MAPANDES/ POTONG GIGI</p>
          <p>putra kami yang akan diselenggarakan pada:</p>
          <div class="font-bold flex flex-col gap-y-2 my-4 uppercase">
            <p class="text-xl">Kamis, 25 Juli 2024</p>
            <p class="text-xl">13:00 Wita - Selesai</p>
            <div class="text-sm">
              <p>Br. Pilisan Kaba - Kaba, </p>
              <p>
                Kediri, Tabanan
              </p>
              <p>
                (Geriya Tandeg Gede)
              </p>
            </div>
          </div>
        </div>
        <div class="my-4" data-aos="fade-up" data-aos-delay="200">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3945.1073097209583!2d115.1467378!3d-8.5856804!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2dd23977309aeeed%3A0x6db984339a269149!2sJl.%20Sentra%20No.36%2C%20Kaba-Kaba%2C%20Kec.%20Kediri%2C%20Kabupaten%20Tabanan%2C%20Bali%2082121!5e0!3m2!1sen!2sid!4v1719412160410!5m2!1sen!2sid"
            width="100%" height="400" style="border:0;" allowfullscreen="" loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"></iframe>
          <button @click="openMap" type="button"
            class="inline-flex items-center gap-x-1.5 rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600 mt-4">
            <MapPinIcon class="-ml-0.5 h-5 w-5" aria-hidden="true" />
            Petunjuk Arah
          </button>
        </div>
        <div class="flex flex-col gap-y-2" data-aos="fade-up" data-aos-delay="300">
          <p>Merupakan suatu kehormatan dan kebahagiaan bagi kami sekeluarga apabila Bapak/Ibu/Saudara/i berkenan hadir
            untuk hadir memberikan doa</p>
          <h1 class="font-dancing-script text-4xl">Om Shanti, Shanti, Shanti Om</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.section {
  background-image: url('./assets/background-modal.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>