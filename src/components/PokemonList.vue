<template>
    <div>
        <ul class="grid grid-cols-1 sm:grid-cols-3 gap-4">
            <li v-for="pokemon in pokemonList" :key="pokemon">
              <div @click="sendToggleFeaturedEmisor(pokemon)" class="flex flex-col justify-between w-[100%] h-[100%] rounded-xl bg-slate-100 shadow-2xl border-2 border-purple-300 overflow-hidden transition-transform duration-300 ease-in-out transform hover:scale-105">
                 <img class="cover p-4" :src="pokemon.sprites.other.dream_world.front_default" :alt="pokemon.name">
                 <h3 class="text-white bg-purple-900 text-center rounded-b-xl p-8">{{pokemon.name}}</h3>
              </div>
            </li>
          </ul>
      
    </div>
</template>
<script>
export default {
    name: "PokemonList",
    props: ["pokemonList"],
    data() {
        return {
            isVisibleFeatured: false
        }
    },
    methods: {
        sendToggleFeaturedEmisor(pokemon) {
        this.$emit("sendedToggleFeaturedSignal", !this.isVisibleFeatured)
        this.$emit("sendedPokemonInfo", pokemon)
        }
    }
}
</script>
