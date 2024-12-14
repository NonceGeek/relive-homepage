<template>
  <div class="flex flex-col w-content mx-auto pt-9">
    <div class="header h-16 flex justify-between items-center">
      <div class="flex items-center space-x-3">
        <h1 class="text-4xl font-bold">Relive 人生重开模拟器</h1>
      </div>
      <div class="links flex items-center space-x-5 text-black-1 dark:text-white font-['Poppins'] text-[17px]">
        <!--<a v-for="link in links" :key="link" class="group relative h-7 flex items-center cursor-pointer">
          <span>{{ link }}</span>
        </a>-->
        <div class="flex justify-center ml-2" @click="toggleColorMode">
          <input type="checkbox" name="light-switch" class="light-switch sr-only" />
          <label
            class="relative h-[30px] p-[3px] bg-[#F0F2F5] dark:bg-[#2C2C2C] rounded-full after:content-[''] after:transition-transform after:duration-500 after:absolute after:dark:translate-x-full after:w-6 after:h-6 after:p-[6px] after:rounded-full after:bg-gradient-to-r after:from-[#439DFF] after:to-[#6052FF] flex items-center cursor-pointer select-none"
            for="light-switch">
            <img class="m-[6px] z-20 w-3 h-3" src="~/assets/svg/light-mode.svg" alt="light-mode">
            <img class="m-[6px] z-20 w-3 h-3" src="~/assets/svg/dark-mode.svg" alt="dark-mode">
            <span class="sr-only">Switch to light / dark version</span>
          </label>
        </div>
      </div>
    </div>
    <div class="slogon mt-12 flex justify-between items-center">
      <div class="flex flex-col space-y-12">
        <div class="texts flex flex-col space-y-6">
          <div class="titles flex flex-col space-y-9">
            <div class="flex flex-col space-y-4 text-black-1 dark:text-white">
              <h3 class="text-4xl font-bold">Multiple Versions of Relive Simulators 🌱</h3>
              <h3 class="text-4xl font-bold">Relive 人生重开模拟器的各种版本 🌱</h3>
              <!--<span class="w-[450px] text-[50px] leading-none font-['Poppins'] font-medium tracking-[0.6px]"><b>Move Game
                Kit</b></span>-->
              <span class="w-[600px] text-[20px] leading-tight font-['Poppins']">AI-based Game - Relive Simulator.</span>
              <span class="w-[600px] text-[20px] leading-tight font-['Poppins']">Generate a new life based on the AI generated events.</span>
            </div>
          </div>
          <div class="flex items-center space-x-2 text-third-gray dark:text-gray-4 text-[20px]">
            <span class="leading-8">
              Powered by <a href="https://x.com/intent/follow?screen_name=0xleeduckgo" target="_blank" rel="noopener noreferrer"
                class="text-blue-500 underline">0xleeduckgo</a>
            </span>
            &nbsp;and other NonceGeekDAO members
            <a href="https://noncegeek.com" target="_blank" rel="noopener noreferrer"><img class="w-8 h-8" src="/img/logo-ng.jpg" alt="noncegeek"></a>
          </div>
        </div>
        <div class="buttons flex items-center space-x-8">
          <template v-for="button in buttons" :key="button.text">
            <TheButton :text="button.text" :uppercase="true" :high="true" :colored-border="button.coloredBorder"
              :change-text="true" :href="button.href" />
          </template>
        </div>
      </div>
      <pre
        class="w-[400px] text-black-1 dark:text-white font-mono cursor-pointer select-none"
        @mouseenter="startMushroomAnimation"
        @mouseleave="stopMushroomAnimation"
      >{{ mushroomArt }}</pre>
    </div>
    <div class="mt-40 mx-auto w-[1160px] flex flex-col items-center space-y-[142px]">

      <!-- A Block Begin -->
      <div class="w-full flex justify-start items-center space-x-60">
        <div class="w-[555px] flex flex-col space-y-6 items-start">
          <div class="w-full flex flex-col space-y-2 text-[20px] text-second-gray dark:text-white font-['Poppins']">
            <div class="flex items-center">
              Relive Simulator on Coze, Free to play!
            </div>
          </div>
          <TheButton text="Launch App" :colored-border="true" href="https://relive.noncegeek.com" />
        </div>

        <div class="title text-black-2 dark:text-white text-[35px] font-['Poppins'] font-semibold flex items-center">
          <span>on Coze(Web2.0) 🐙</span>
        </div>

      </div>
      <div class="w-[575px] p-2.5">
        <LinearLine />
      </div>
      <!-- A Block End -->

      <!-- B Block Begin -->
      <div class="w-full flex justify-start items-center space-x-[400px]">
        <div class="title text-black-2 dark:text-white text-[40px] font-['Poppins'] font-semibold flex items-center">
          <span class="w-[200px]">on AO 🐱</span>
        </div>
        <div class="w-[600px] flex flex-col space-y-6 items-start">
          <div class="w-full flex flex-col space-y-2 text-[20px] text-second-gray dark:text-white font-['Poppins']">
            <div class="flex items-center">
              Relive Simulator on AO.
            </div>
            <div class="flex items-center">
              Integrate with the DID & Achievement Board.
            </div>
          </div>

          <TheButton text="Launch App" :colored-border="true" href="https://relife.rootmud.xyz/" />
          <TheButton text="Demo Video" :colored-border="true" href="https://www.youtube.com/watch?v=wi4DpYdHFNI" />
        </div>
      </div>
      <div class="w-[575px] p-2.5">
        <LinearLine />
      </div>
      <!-- B Block End -->

      <!-- A Block Begin -->
      <div class="w-full flex justify-start items-center space-x-60">
        <div class="w-[555px] flex flex-col space-y-6 items-start">
          <div class="w-full flex flex-col space-y-2 text-[20px] text-second-gray dark:text-white font-['Poppins']">
            <div class="flex items-center">
              Impl under EVM Stack.
            </div>
          </div>

          <TheButton text="Launch App" :colored-border="true" href="https://evm.relife.rootmud.xyz" />
        </div>

        <div class="title text-black-2 dark:text-white text-[40px] font-['Poppins'] font-semibold flex items-center">
          <span>on EVM 🦌</span>

        </div>

      </div>
      <div class="w-[575px] p-2.5">
        <LinearLine />
      </div>
      <!-- A Block End -->

      <!-- A Block Begin -->
      <div class="w-full flex justify-start items-center space-x-[500px]">
        <div class="title text-black-2 dark:text-white text-[40px] font-['Poppins'] font-semibold flex items-center">
          <span>on Move 🦀</span>
        </div>
        
        <div class="w-[400px] flex flex-col space-y-6 items-start">
          <div class="w-full flex flex-col space-y-2 text-[20px] text-second-gray dark:text-white font-['Poppins']">
            <div class="flex items-center">
              Experience the Move Games!
            </div>
          </div>

          <TheButton text="TBD: Launch App on Movement" :colored-border="true" href="https://nocnegeek.com" />
          <TheButton text="TBD: Launch App on Rooch" :colored-border="true"
            href="https://nocnegeek.com" />
        </div>
      </div>
      <!-- B Block End -->

    </div>




    <!-- Footer -->
    <div class="footer mt-60 pb-24 flex flex-col space-y-3">
      <LinearLine />
      <div class="flex justify-between items-center text-third-gray dark:text-white font-['Montserrat']">
        <span v-for="text in footerTexts" :key="text">{{ text }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const links = [
  'Twitter',
]
const buttons = [
  {
    text: 'Github',
    coloredBorder: false,
    href: 'https://github.com/NonceGeek/relive-homepage',
  },
  // {
  //   text: 'Whitepaper-EN',
  //   coloredBorder: false,
  //   href: 'https://bodhi.wtf/space/5/15427',
  // },
  // {
  //   text: 'Whitepaper-CN',
  //   coloredBorder: false,
  //   href: 'https://bodhi.wtf/space/5/15426',
  // },
  {
    text: 'Video',
    coloredBorder: false,
    href: 'https://www.youtube.com/watch?v=wi4DpYdHFNI',
  },
]
const footerTexts = [
  'ཨོཾ་མཱ་རི་ཙྱཻ་སྭཱ་ཧཱ། Copyright © 2024 NonceGeekDAO & rootMUD DAO. All rights reserved. ཨོཾ་མཱ་རི་ཙྱཻ་སྭཱ་ཧཱ།',
  'Terms of Use & Privacy Policy',
]

const colorMode = useColorMode('dark');
const toggleColorMode = () => {
  if (colorMode.preference === 'dark') {
    colorMode.preference = 'light'
  } else {
    colorMode.preference = 'dark'
  }
}

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}

const mushroomTypes = ['red', 'yellow', 'blue', 'green'];
let currentIndex = 0;
let intervalId = null;

const currentMushroomSrc = ref(`/img/mushroom-${mushroomTypes[currentIndex]}.png`);

const changeMushroomColor = () => {
  currentIndex = (currentIndex + 1) % mushroomTypes.length;
  currentMushroomSrc.value = `/img/mushroom-${mushroomTypes[currentIndex]}.png`;
};

const startMushroomAnimation = () => {
  if (!intervalId) {
    intervalId = setInterval(changeMushroomColor, 500);
  }
};

const stopMushroomAnimation = () => {
  if (intervalId) {
    clearInterval(intervalId);
    intervalId = null;
  }
};

const mushroomArt = `　　 ∩＿＿＿∩
　　 | ノ　　　　　 ヽ
　　/　　●　　　● |　YEEHA!!
　 |　　　　( _●_)　 ミ
　彡､　　　|∪|　　､｀＼
/　＿＿　 ヽノ　/´>　 )
(＿＿＿）　　　/　(_／
　|　　　　　　 /
　|　　／＼　＼
　|　/　　　 )　 )
　∪　　　 （　 ＼
　　　　　　 ＼＿)
`
</script>

<style scoped></style>
