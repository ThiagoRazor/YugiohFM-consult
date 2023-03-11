<template>
    <section class="w-5/4 m-auto overflow-hidden text-neutral-700">
        <div class="flex justify-center">
            <div class="flex mb-3 xl:w-96">
                <input v-model="searchCard" type="text"
                @keydown.enter="searchCardByName()"
                    class="relative m-0 block w-full min-w-0 flex-auto rounded border border-solid border-neutral-300 bg-zinc-100 bg-clip-padding px-3 py-1.5 text-base font-normal outline-none transition duration-300 ease-in-out focus:border-primary-600 focus:text-neutral-700 focus:shadow-te-primary focus:outline-none dark:border-neutral-600 dark:text-neutral-200 placeholder:text-black"
                    placeholder="Search Card" />
            </div>
        </div>
        <div>{{ searchCard }}</div>
        <div class="container mx-auto px-2 py-2 lg:px-32 lg:pt-12">
            <div class=" border-solid -m-1 flex flex-wrap md:-m-2">
                <div class="flex rounded-xl m-auto">
                    <div  class="flex flex-wrap gap-8 justify-center w-full rounded-xl h-62 p-2 md:p-2 ">
                        <div  v-for="i in cardInfo.length " :key="i" class="cursor-pointer flex flex-col gap-2"
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
import cardInfo from '../cardInfo.json'

export default {
    data(){
        return{
            searchCard: '',
            cardInfo: cardInfo,        
            searchResult:[]
        }
    },
    methods:{
        searchCardByName(){
  this.searchResult = this.cardInfo.filter(card => {
    return card.name.toLowerCase().includes(this.searchCard.toLowerCase());
  })
  console.log(this.searchResult.length)
  var numObj = this.searchResult.length;

  for (var i = 0; i < numObj; i++){
    console.log("Id: " + this.searchResult[i].id);
    console.log("Name: " + this.searchResult[i].name);
    console.log("Stars:" + this.searchResult[i].price);
  }
},

    }
}
</script>
    