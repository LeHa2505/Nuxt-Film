<template>
  <div class="container">
    <div class="direction">
      <button id="prev">&lt;</button>
    </div>
    <div id="formList">
      <div id="list">
        <div class="item" v-for="(film, index) in films" :key="index">
          <div class="getWidth">
            <img :src="film.img" class="avatar" />
            <div class="content">
              <p>{{ film.title }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="direction">
      <button id="next">&gt;</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      films: [
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
      ],
    };
  },
  mounted() {
    document.getElementById("next").onclick = function () {
      const widthItem = document.querySelector(".getWidth").offsetWidth;
      document.getElementById("formList").scrollLeft += widthItem;
    };
    document.getElementById("prev").onclick = function () {
      const widthItem = document.querySelector(".getWidth").offsetWidth;
      document.getElementById("formList").scrollLeft -= widthItem;
    };
  },
};
</script>

<style scoped>
.getWidth {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.content p {
  margin-top: 0;
}
.direction {
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}
.direction button {
  font-family: cursive;
  font-weight: bold;
  background-color: #ffffff44;
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  transition: 0.5s;
  margin: 0 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.direction button:hover {
  background-color: #ffffff;
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
  width: max-content;
}
#formList {
  width: 1280px;
  max-width: 100%;
  overflow: auto;
  scroll-behavior: smooth;
  scroll-snap-type: both;
}
#formList::-webkit-scrollbar {
  display: none;
}

#prev,
#next {
  font-size: 32px;
}
</style>
