<script setup>
import { ref, onMounted } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

import MenuItem from './components/MenuItem.vue';
import MusicPlayer from './components/MusicPlayer.vue';
import ChevronUp from 'vue-material-design-icons/ChevronUp.vue';
import ChevronDown from 'vue-material-design-icons/ChevronDown.vue';
import ChevronRight from 'vue-material-design-icons/ChevronRight.vue';
import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue';

import { useSongStore } from './stores/song'
import { storeToRefs } from 'pinia';
const useSong = useSongStore()
const { isPlaying, currentTrack } = storeToRefs(useSong)

onMounted(() => { isPlaying.value = false })

let openMenu = ref(false)
</script>

<template>
  <div>
    <div class="w-[calc(100%-240px)] 
    h-[60px] 
    fixed 
    right-0 
    z-20 
    bg-[#101010] 
    bg-opacity-80 
    flex 
    flex-col 
    items-end 
    justify-center">
      <button @click="openMenu = !openMenu" :class="openMenu ? 'bg-[#282828]' : 'bg-black'"
        class="bg-black hover:bg-[#282828] rounded-full p-0.5 mr-8 mt-0.5 cursor-pointer">
        <div class="flex items-center">
          <img class="rounded-full" width="27"
            src="https://yt3.ggpht.com/yti/ANjgQV8HuQRln_3dN4icnmKLJ-xCzKI2UOyXNJEUxHCJZaw=s88-c-k-c0x00ffffff-no-rj">
          <div class="text-white text-[14px] ml-1.5 font-semibold">Văn Lê</div>
          <ChevronDown v-if="!openMenu" @click="openMenu = true" fillColor="#FFFFFF" :size="25" />
          <ChevronUp v-else @click="openMenu = false" fillColor="#FFFFFF" :size="25" />
        </div>
      </button>
      <span v-if="openMenu"
        class="fixed w-[190px] bg-[#282828] shadow-2xl z-50 rounded-sm top-[52px] right-[35px] p-1 cursor-pointer">
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D] border-b border-b-gray-600">Profile</li>
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D]">Log out</li>
        </ul>
      </span>
    </div>

    <div id="SideNav" class="h-[100%] p-6 w-[240px] fixed z-50 bg-black">
      <RouterLink to="/">
        <img width="125" src="/images/icons/spotify-logo.png">
      </RouterLink>
      <div class="my-8"></div>
      <ul>
        <RouterLink to="/">
          <MenuItem class="ml-[1px]" :iconSize="23" name="Trang chủ" iconString="home" pageUrl="/" />
        </RouterLink>
        <RouterLink to="/search">
          <MenuItem class="ml-[1px]" :iconSize="24" name="Tìm kiếm" iconString="search" pageUrl="/search" />
        </RouterLink>
        <RouterLink to="/library">
          <MenuItem class="ml-[2px]" :iconSize="23" name="Thư viện của tôi" iconString="library" pageUrl="/library" />
        </RouterLink>
        <div class="py-3.5"></div>
        <MenuItem :iconSize="24" name="Tạo album nhạc" iconString="playlist" pageUrl="/playlist" />
        <MenuItem class="-ml-[1px]" :iconSize="27" name="Những bài hát ưa thích của tôi" iconString="liked" pageUrl="/liked" />
      </ul>
      <div class="border-b border-b-gray-700"></div>
    </div>
  </div>
  <div class="
            fixed
            right-0
            top-0
            w-[calc(100%-240px)]
            overflow-auto
            h-full
            bg-gradient-to-b
            from-[#1C1C1C]
            to-black
        ">
    <div class="mt-[70px]"></div>
    <RouterView />
    <div class="mb-[100px]"></div>
  </div>

  <MusicPlayer v-if="currentTrack"/>
</template>
