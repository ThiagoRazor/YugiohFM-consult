<template>
    <div>
        <span class="w-2/4 text-black capitalize bg-amber-300 p-2 rounded-xl">Nº: 1 </span>
        <img class="m-auto block h-62 w-32 rounded-lg object-cover object-center" :src="imageSrc" />
    </div>
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