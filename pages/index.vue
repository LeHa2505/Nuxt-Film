<template>
  <div>
    <el-carousel height="700px">
      <el-carousel-item v-for="(film, index) in listFilmIntro" :key="index">
        <div class="item">
          <div class="item__content">
            <h1>{{ film.title }}</h1>
            <p>
              {{ film.desc }}
            </p>
            <el-row>
              <el-button type="success" round
                >WATCH NOW
                <font-awesome-icon :icon="['fass', 'circle-play']" style="margin-left: 5px"/></el-button>
              <el-button type="danger" round
                >WATCH TRAILER
                <font-awesome-icon :icon="['fas', 'film']"  style="margin-left: 5px"/>
                </el-button>
            </el-row>
          </div>
          <img class="item__image" :src="film.img" alt="" />
        </div>
      </el-carousel-item>
    </el-carousel>

    <div style="padding: 0 160px">
      <TitleList content="Films Up Comming" />
      <UpCommingFilm />
    </div>

    <div style="padding: 0 160px">
      <TitleList content="Films Top" />
      <CardSlider />
    </div>

    <div style="padding: 0 160px">
      <TitleList content="Films Popular" />
      <ListFilmsPopular/>
      
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  
  data() {
    return {
      listFilmIntro: [
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
      
    };
  },
  
};
</script>

<style scoped>
.item {
  position: relative;
  height: 100%;
}

.item__content {
  position: absolute;
  bottom: auto;
  top: 200px;
  width: 55%;
  left: 100px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  /* background: rgba(0, 0, 0, 0.5); */
  color: #fff;
  padding: 3px;
}

.item__image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>
