<template>
  <section class="recipes">
    <Recipe 
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText"
    />
  </section>
</template>

<script>

import Recipe from '@/components/Recipe'
 
export default {
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "food-one",
              thumbnail: "https://static.independent.co.uk/s3fs-public/thumbnails/image/2017/02/07/15/chinese.jpg",
              title: "Delecious Food",
              previewText: "Cool food for the body"
            },
            {
              id: "food-two",
              thumbnail: "https://assets3.thrillist.com/v1/image/2815308/size/tmg-article_default_mobile.jpg",
              title: "Delicious chicken",
              previewText: "Cool food for the body"
            }
          ]
        })
      }, 1000)
    })
  }
}
</script>


<style scoped>
  .recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
  }

 
</style>
