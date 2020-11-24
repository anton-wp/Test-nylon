<template>
  <div class="block-wrapper">
    <div class="big-block">
      <a class="big-block__news-card" href="#">
        <div>
          <p class="big-block__category monospace">
            {{ newsBlockBig.category }}
          </p>
          <p class="big-block__title">{{ newsBlockBig.title }}</p>
        </div>
        <div>
          <img class="big-block__image" :src="newsBlockBig.image" alt="sorry" />
        </div>
        <div></div>
      </a>
      <div class="news-left">
        <a
          v-for="(news, index) in newsBlockSmall.slice(0, 2)"
          :key="index"
          :href="news.slug"
          class="small-card__link"
        >
          <NewsBlock :data="news" />
        </a>
      </div>
    </div>
    <div class="small-block">
      <a
        v-for="(news, index) in newsBlockSmall.slice(2, 4)"
        :key="index"
        :href="news.slug"
        class="small-card__link"
      >
        <NewsBlock :data="news" />
      </a>
    </div>
  </div>
</template>

<script>
import NewsBlock from "@/components/NewsBlock";

export default {
  components: {
    NewsBlock,
  },
  head: {
    link: [
      {
        rel: "stylesheet",
        href:
          "//db.onlinewebfonts.com/c/13a1076b1b32d14d28f72760640fbe08?family=Post+Grotesk",
        type: "text/css",
      },
      {
        rel: "stylesheet",
        href:
          "//db.onlinewebfonts.com/c/a3897dd4acd4ea7bf55831db40dcaab1?family=Monospace+821",
        type: "text/css",
      },
    ],
  },
  data: () => ({
    newsBlockSmall: [
      {
        category: "Beauty",
        image:
          "https://imgix.bustle.com/uploads/image/2020/11/13/03465aed-6a19-46dc-a81e-ec979103d04b-1116_marcela.jpg?w=200&h=147&auto=format%2Ccompress&cs=srgb&q=70&fit=crop&crop=faces",
        title:
          "“Grand Army” Star Marcela Avelina On Her Greatest Beauty Discovery And the Power of Vulnerability",
        slug: "#",
      },
      {
        category: "Entertainment",
        image:
          "https://imgix.bustle.com/uploads/image/2020/11/16/03a0d921-a828-43aa-8985-625f1ccf151c-fullsizerender-1.jpeg?w=200&h=300&auto=format%2Ccompress&cs=srgb&q=70&fit=crop&crop=faces",
        title:
          "Serena Isioma's Chicago-Based Indie Is Refreshing & Straight To The Point",
        slug: "#",
      },
      {
        category: "Fashion",
        image:
          "https://imgix.bustle.com/uploads/image/2020/11/13/a922f3b4-e87f-4dfb-a433-4985f9afb92a-nylonnineteen_jillianmercado.jpg?w=200&h=171&auto=format%2Ccompress&cs=srgb&q=70&fit=crop&crop=faces",
        title:
          "Jillian Mercado On Dog Memes, Elsa Majimbo, And Going To A Fall Out Boy Concert By Herself",
        slug: "#",
      },
      {
        category: "Life",
        image:
          "https://imgix.bustle.com/uploads/image/2020/11/16/bb332db1-d8c7-4a74-bc2f-38a869d5ed67-new-moon.png?w=200&h=165&auto=format%2Ccompress&cs=srgb&q=70&fit=crop&crop=faces",
        title: "The New Moon In Scorpio Reminds You To Keep The Faith",
        slug: "#",
      },
    ],
    newsBlockBig: {
      category: "Fashion",
      image:
        "https://imgix.bustle.com/uploads/image/2020/11/11/ae3b97ea-5fdc-4c1c-8723-15f64d89ace0-1112_pinterest.jpg?w=792&h=554&auto=format%2Ccompress&cs=srgb&q=70&fit=crop&crop=faces",
      title:
        "How Pinterest Became Gen Z's Favorite Source Of Fashion Inspiration",
    },
  }),
};
</script>

<style lang="scss">
:root {
  --pageGutter: 1rem;
  --maxContainerWidth: 1320px;
}
.block-wrapper {
  $root: &;

  color: black;
  margin: 0 auto;
  max-width: var(--maxContainerWidth);
  padding: 2rem var(--pageGutter);
  position: relative;
  width: 100%;
  box-sizing: border-box;

  @media (min-width: 1352px) {
    padding-left: 0;
    padding-right: 0;
  }
  @media (min-width: 768px) {
    align-items: flex-start;
    display: flex;
    flex-wrap: wrap;
    padding-bottom: 4rem;
    padding-top: 4rem;
  }
  a {
    text-decoration: none;
    word-break: break-word;
  }

  .big-block {
    color: black;

    @media (min-width: 768px) {
      align-items: flex-start;
      display: flex;
      flex-direction: row-reverse;
      flex: 1 0 calc(100% - 150px);
    }
    @media (min-width: 1025px) {
      flex: 1 0 calc(100% - 200px);
    }
    &__news-card {
      border-top: 1px solid;
      display: block;
      padding-bottom: 2rem;
      text-decoration: none;
      color: inherit;

      @media (min-width: 768px) {
        flex: 1;
        margin: 0 1.5rem;
        padding-bottom: 0;
      }
      @media (min-width: 1025px) {
        margin: 0 3rem;
      }
    }
    &__image {
      width: 100%;
      object-fit: cover;
    }
    &__category {
      font-weight: 400;
      color: inherit;
      font-size: 0.7rem;
      margin: 1.2rem 0;
      text-transform: uppercase;
    }
    &__title {
      letter-spacing: -0.04em;
      line-height: 1;
      text-transform: uppercase;
      overflow: hidden;
      font-weight: 400;
      display: block;
      font-size: 2.5rem;
      margin: 0 auto 1.5rem 20%;
      text-align: right;

      @media (min-width: 1025px) {
        flex: 1;
        font-size: 3rem;
        margin: -2.2rem 0 1.5rem 10%;
      }
    }

    .news-left {
      align-items: baseline;
      display: flex;
      flex: 1 0 40%;
      flex-wrap: wrap;
      @media (min-width: 1025px) {
        flex: 0 0 200px;
      }
      @media (min-width: 768px) {
        flex: 0 0 150px;
        align-items: flex-start;
        display: flex;
        flex-direction: column;
      }
    }
  }
  .small-block {
    flex-wrap: wrap;
    display: flex;

    @media (min-width: 1025px) {
      flex: 0 0 200px;
    }
    @media (min-width: 768px) {
      flex: 0 0 150px;
      align-items: flex-start;
      display: flex;
      flex-direction: column;
    }
    .small-card {
      &__category {
        margin: 0.95rem 0;
      }
      &__link {
        flex: 1 0 calc(50% - 0.5rem);
      }
    }
  }
}
.small-card {
  @media (max-width: 768px) {
    &__link {
      flex: 1 0 calc(50% - 0.5rem);
      &:nth-child(2n) {
        margin-left: 0.5rem;
      }
      &:nth-child(odd) {
        margin-right: 0.5rem;
      }
    }
  }
}
</style>