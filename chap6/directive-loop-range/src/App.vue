<template>
  <section>
    <ul>
      <li v-for="r in 5" :key="r">半径{{ r }}の円の円周: {{ 2 * r * 3.14 }}</li>
    </ul>
  </section>

  <section>
    <select>
      <option v-for="year in 60" :key="year" :value="year + 1965">{{ year + 1965 }}年</option>
    </select>
  </section>
</template>
