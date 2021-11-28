<template>
  <div>
    <main>
      <h1>{{ title }}</h1>
      <ul>
        <li v-for="categoryItem in category" :key="categoryItem.id">
          {{ categoryItem.categoryName }}
        </li>
      </ul>
      <div v-html="content"></div>
    </main>
  </div>
</template>

<script>
export default {
  async asyncData({ params, $microcms }) {
    const data = await $microcms.get({
      endpoint: 'gsap',
      contentId: params.slug,
    });
    return data;
  },
};
</script>
