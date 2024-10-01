<script setup>
import HomeCard from '../components/HomeCard.vue';
</script>

<template>
    <div class="p-8">
        <button type="button" class="text-white text-2xl font-semibold hover:underline cursor-pointer">
            Những album đang thịnh hành
        </button>

        <div class="py-1.5"></div>

        <div class="flex items-center">
            <HomeCard image="https://picsum.photos/id/22/300/300" title="Lạc lõng" subTitle="Album nhạc" />
            <HomeCard image="https://i.scdn.co/image/ab67616d00001e02d40a324fdd93007b92d29099" title="Anh trai say hi" subTitle="Album nhạc" />
            <HomeCard class="md:block hidden" image="https://i.scdn.co/image/ab67616d00001e021d1d760396010c209a7a9019" title="Xoay một vòng"
                subTitle="Album nhạc" />
            <HomeCard class="lg:block hidden" image="https://i.scdn.co/image/ab67616d00001e02ff825e8af61dad96490e8192" title="Nghe như tình yêu"
                subTitle="Album nhạc" />
            <HomeCard class="xl:block hidden" image="https://i.scdn.co/image/ab67616100005174e3a2b64c22a325875a3710f1" title="Những đứa trẻ"
                subTitle="Album nhạc" />
        </div>
    </div>

    <div class="p-8">
        <button type="button" class="text-white text-2xl font-semibold hover:underline cursor-pointer">
            Radio gợi ý
        </button>

        <div class="py-1.5"></div>

        <div class="flex items-center">
            <HomeCard image="https://picsum.photos/id/120/300/300" title="Radio chữa lành #1" subTitle="Radio" />
            <HomeCard image="https://picsum.photos/id/110/300/300" title="Radio chữa lành #2" subTitle="Radio" />
            <HomeCard class="md:block hidden" image="https://picsum.photos/id/221/300/300" title="Radio chữa lành #3"
                subTitle="Radio" />
            <HomeCard class="lg:block hidden" image="https://picsum.photos/id/232/300/300" title="Radio chữa lành #4"
                subTitle="Radio" />
            <HomeCard class="xl:block hidden" image="https://picsum.photos/id/187/300/300" title="Radio chữa lành #5"
                subTitle="Radio" />
        </div>
    </div>

    <div class="p-8">
        <button type="button" class="text-white text-2xl font-semibold hover:underline cursor-pointer">
            Những bài hát gợi ý
        </button>

        <div class="py-1.5"></div>

        <div class="flex items-center">
            <HomeCard image="https://picsum.photos/id/88/300/300" title="Bài hát #1" subTitle="Bài hát" />
            <HomeCard image="https://picsum.photos/id/243/300/300" title="Bài hát #2" subTitle="Bài hát" />
            <HomeCard class="md:block hidden" image="https://picsum.photos/id/123/300/300" title="Bài hát #3"
                subTitle="Bài hát" />
            <HomeCard class="lg:block hidden" image="https://picsum.photos/id/121/300/300" title="Bài hát #4"
                subTitle="Bài hát" />
            <HomeCard class="xl:block hidden" image="https://picsum.photos/id/99/300/300" title="Bài hát #5"
                subTitle="Bài hát" />
        </div>
    </div>
</template>