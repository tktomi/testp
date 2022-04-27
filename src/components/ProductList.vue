<template>
  <div>
    <v-row>
      <product
        v-for="(product, key) in filterdList"
        :key="key"
        :product="product"
      >
      </product
    ></v-row>
  </div>
</template>

<script>
import Product from './Product.vue';
export default {
  name: 'ProductList',
  components: { Product },
  data: () => ({
    sortYear: '全て',
    products: [
      {
        id: 1,
        name: 'ここにタイトルを入れてね',
        // TODO: ここに差し替えたい画像のパスを入れてね
        image: require('@/assets/re-vr.png'),
        year: '2020',
        category: 'プロジェクト',
        use: 'ここに使った技術を入れてね',
        urls: [
          // TODO: ここにリンクしたいURLを入れてね
          'http://google.com'
        ],
      },
      // image: "vue-portfolio/src/assets/re-vr.png",
      // {
      //   id: 2,
      //   name: "work2",
      //   image: "https://dummyimage.com/250x150/000/fff",
      //   year: "2019",
      //   category: "LP",
      //   use: "Vue.js",
      // },
      // {
      //   id: 3,
      //   name: "work3",
      //   image: "https://dummyimage.com/250x150/000/fff",
      //   year: "2018",
      //   category: "ECサイト",
      //   use: "デザイン",
      // },
      // {
      //   id: 4,
      //   name: "work4",
      //   image: "https://dummyimage.com/250x150/000/fff",
      //   year: "2019",
      //   category: "LP",
      //   use: "Vue.js",
      // },
    ],
  }),
  computed: {
    filterdList: function() {
      const newList = [];
      for (let i = 0; i < this.products.length; i++) {
        if (this.sortYear === "2020" && this.products[i].year === "2020") {
          newList.push(this.products[i]);
        } else if (
          this.sortYear === "2019" &&
          this.products[i].year === "2019"
        ) {
          newList.push(this.products[i]);
        } else if (
          this.sortYear === "2018" &&
          this.products[i].year === "2018"
        ) {
          newList.push(this.products[i]);
        } else if (this.sortYear === "全て") {
          newList.push(this.products[i]);
        }
      }
      return newList;
    },
  },
  methods: {
    sortYearChanged: function(year) {
      console.log(year);
      this.sortYear = year;
    },
  },
};
</script>
