<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" alt="">
    </div>
    <p>The recipe description</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
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
          ].find(el => el.id === context.params.id)
        })
      }, 1000)
    })
  }
}
</script>


<style scoped>
  /* style the single-recipe class */
  .single-recipe {
    display: flex;
    flex-flow: column wrap;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
  }

  .recipe-image {
    width: 100%;
  }
</style>
