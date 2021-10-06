<template>
  <div>
      <!-- <table>
          <thead>
              <tr>
                <th>
                    Pockemon name
                </th>
              </tr>
          </thead>
          <tbody>
              <tr v-for="pokemon in pokemons " :key="pokemon">
                  <th >
                      {{ pokemon }}
                  </th>
              </tr>
          </tbody>
      </table> -->

      <ul>
          <li v-for="(pokemon, index) in pokemons" :key="index">
            {{ pokemon.name }}
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    props: ['pokemons']
}
</script>

<style>

</style>