<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/gsap/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
export default {
  async asyncData({ params, $microcms }) {
    const data = await $microcms.get({
      endpoint: 'gsap',
      contentId: params.slug,
      // queries: { limit: 20, filters: 'createdAt[greater_than]2021' },
    });
    return data;
  },
};
</script>
