<template>
  <div id="formList">
    <div id="list">
      <div style="display: flex; flex-direction: row; flex-wrap: wrap; justify-content: center;">
        <div
          class="item"
          v-for="(film, index) in pagedListFilmsPopular"
          :key="index"
        >
          <div class="getWidth">
            <img :src="film.img" class="avatar" />
            <div class="content">
              <p>{{ film.title }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <el-pagination
      background
      layout="prev, pager, next"
      :total="this.listFilmsPopular.length"
      @current-change="setPage"
    >
    </el-pagination>
  </div>
</template>

<script>
export default {
  created() {
    for (let i = 0; i < 100; i++) {
      this.tableData.push({
        date: "2016-05-03",
        name: "Tom",
        address: `No. ${i}, Grove St, Los Angeles`,
      });
    }
  },
  data() {
    return {
      listFilmsPopular: [
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/Ab8mkHmkYADjU7wQiOkia9BzGvS.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/dIWwZW7dJJtqC6CgWzYkNVKIUm8.jpg",
        },
        {
          title: "Primal: Tales of Savagery",
          desc: "Genndy Tartakovsky's Primal: Tales of Savagery features a caveman and a dinosaur on the brink of extinction. Bonded by tragedy, this unlikely friendship becomes the only hope of survival.",
          img: "https://image.tmdb.org/t/p/original/uBZQOYZLIU9dBmd62fdzBAoropu.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/Ab8mkHmkYADjU7wQiOkia9BzGvS.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/dIWwZW7dJJtqC6CgWzYkNVKIUm8.jpg",
        },
        {
          title: "Primal: Tales of Savagery",
          desc: "Genndy Tartakovsky's Primal: Tales of Savagery features a caveman and a dinosaur on the brink of extinction. Bonded by tragedy, this unlikely friendship becomes the only hope of survival.",
          img: "https://image.tmdb.org/t/p/original/uBZQOYZLIU9dBmd62fdzBAoropu.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/Ab8mkHmkYADjU7wQiOkia9BzGvS.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/dIWwZW7dJJtqC6CgWzYkNVKIUm8.jpg",
        },
        {
          title: "Primal: Tales of Savagery",
          desc: "Genndy Tartakovsky's Primal: Tales of Savagery features a caveman and a dinosaur on the brink of extinction. Bonded by tragedy, this unlikely friendship becomes the only hope of survival.",
          img: "https://image.tmdb.org/t/p/original/uBZQOYZLIU9dBmd62fdzBAoropu.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/Ab8mkHmkYADjU7wQiOkia9BzGvS.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/dIWwZW7dJJtqC6CgWzYkNVKIUm8.jpg",
        },
        {
          title: "Primal: Tales of Savagery",
          desc: "Genndy Tartakovsky's Primal: Tales of Savagery features a caveman and a dinosaur on the brink of extinction. Bonded by tragedy, this unlikely friendship becomes the only hope of survival.",
          img: "https://image.tmdb.org/t/p/original/uBZQOYZLIU9dBmd62fdzBAoropu.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/Ab8mkHmkYADjU7wQiOkia9BzGvS.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/dIWwZW7dJJtqC6CgWzYkNVKIUm8.jpg",
        },
        {
          title: "Primal: Tales of Savagery",
          desc: "Genndy Tartakovsky's Primal: Tales of Savagery features a caveman and a dinosaur on the brink of extinction. Bonded by tragedy, this unlikely friendship becomes the only hope of survival.",
          img: "https://image.tmdb.org/t/p/original/uBZQOYZLIU9dBmd62fdzBAoropu.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/Ab8mkHmkYADjU7wQiOkia9BzGvS.jpg",
        },
        {
          title: "Spirited Away",
          desc: "A young girl, Chihiro, becomes trapped in a strange new world of spirits. When her parents undergo a mysterious transformation, she must call upon the courage she never knew she had to free her family.",
          img: "https://image.tmdb.org/t/p/original/dIWwZW7dJJtqC6CgWzYkNVKIUm8.jpg",
        },
        {
          title: "Primal: Tales of Savagery",
          desc: "Genndy Tartakovsky's Primal: Tales of Savagery features a caveman and a dinosaur on the brink of extinction. Bonded by tragedy, this unlikely friendship becomes the only hope of survival.",
          img: "https://image.tmdb.org/t/p/original/uBZQOYZLIU9dBmd62fdzBAoropu.jpg",
        },
      ],
      tableData: [],
      page: 1,
      pageSize: 12,
    };
  },
  computed: {
    pagedListFilmsPopular() {
      return this.listFilmsPopular.slice(
        this.pageSize * this.page - this.pageSize,
        this.pageSize * this.page
      );
    },
  },
  methods: {
    setPage(val) {
      this.page = val;
    },
  },
};
</script>

<style scoped>
.content p {
  margin-top: 0;
}
.item {
  border-radius: 15px;
  width: 250px;
  overflow: hidden;
  transition: 0.5s;
  margin: 10px;
  scroll-snap-align: start;
}
.item .avatar {
  display: block;
  margin: 25px auto 10px;
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 20px;
}
.item .content {
  font-weight: 900;
  font-size: 16px;
  color: #fff;
}
.item .content table td {
  padding: 10px 0;
  border-bottom: 1px solid #aec0ce;
}
.item .content table td:nth-child(2) {
  text-align: right;
}
.item .nameGroup {
  text-align: center;
  border-bottom: none !important;
}
#list {
  display: flex;
  width: -moz-max-content;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}
#formList {
  width: 1280px;
  max-width: 100%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}
#formList::-webkit-scrollbar {
  display: none;
}

.getWidth {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
