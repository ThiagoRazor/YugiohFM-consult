<template>
    <section class="w-5/4 m-auto overflow-hidden text-neutral-700">
        <div class="flex justify-center">
            <div class="flex mb-3 xl:w-96">
                <input v-model="searchCard" type="text"
                    class="relative m-0 block w-full min-w-0 flex-auto rounded border border-solid border-neutral-300 bg-zinc-100 bg-clip-padding px-3 py-1.5 text-base font-normal outline-none transition duration-300 ease-in-out focus:border-primary-600 focus:text-neutral-700 focus:shadow-te-primary focus:outline-none dark:border-neutral-600 dark:text-neutral-200 placeholder:text-black"
                    placeholder="Search Card" />
            </div>
        </div>
        <div class="container mx-auto px-2 py-2 lg:px-32 lg:pt-12">
            <div class=" border-solid -m-1 flex flex-wrap md:-m-2">
                <div class="flex rounded-xl m-auto">
                    <div  class="flex flex-wrap gap-8 justify-center w-full rounded-xl h-62 p-2 md:p-2 ">
                        <div  v-for="i in 722 " :key="i" class="cursor-pointer flex flex-col gap-2"
                             >
                            <span class="w-2/4 text-zinc-800 text-sm text-black font-bold flex justify-center capitalize bg-zinc-400 py-2 rounded-xl">Nº: {{ i }} </span>
                            <img class="m-auto block h-62 w-32 rounded-lg object-cover object-center" :src="'https://raw.githubusercontent.com/ThiagoRazor/YugiohFM-consult/main/public/imgs/' + i + '.jpg'" />
                         </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>


<script>

export default {
    props: {
        imageSrc: {
            type: String,
            required: true,
        }
    }
}
</script>
    