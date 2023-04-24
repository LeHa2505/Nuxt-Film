<template>
  <div style="padding: 20px 160px">
    <el-row :gutter="20">
      <el-col :span="16"
        ><div class="grid-content bg-purple">
          <iframe
            width="100%"
            height="450"
            src="https://www.youtube.com/embed/P4YE-s_8L1Q"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe></div
      ></el-col>
      <el-col :span="1"></el-col>
      <el-col :span="7"
        ><div class="grid-content bg-purple">
          <h2>Recommended</h2>
          <div class="list_film_recommended">
            <div
              class="film_recommended"
              v-for="(film, index) in listFilmsRecommended"
              :key="index"
            >
              <el-row :gutter="20">
                <el-col :span="4"
                  ><div class="grid-content bg-purple">
                    <img
                      :src="film.img"
                      alt="mario"
                      style="width: 100%; border-radius: 6px"
                    /></div
                ></el-col>
                <el-col :span="20"
                  ><div class="grid-content bg-purple">
                    <p style="margin: 6px 0">
                      <strong>{{ film.title }}</strong>
                    </p>
                    <div></div>
                    <el-rate
                      v-model="film.value"
                      disabled
                      text-color="#ff9900"
                      score-template="{film.value} points"
                    >
                    </el-rate></div
                ></el-col>
              </el-row>
            </div>
          </div></div
      ></el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listFilmsRecommended: [
        {
          title: "Aladdin",
          img: "https://image.tmdb.org/t/p/original/fhyun1mja3WwQsYr1a3x1x9BttP.jpg",
          value: 3.7,
        },
        {
          title: "The Little Mermaid",
          img: "https://image.tmdb.org/t/p/original/plcZXvI310FkbwIptvd6rqk63LP.jpg",
          value: 4.2,
        },
        {
          title: "Cinderella",
          img: "https://image.tmdb.org/t/p/original/avz6S9HYWs4O8Oe4PenBFNX4uDi.jpg",
          value: 5,
        },
        {
          title: "Alice in Wonderland",
          img: "https://image.tmdb.org/t/p/original/20cvfwfaFqNbe9Fc3VEHJuPRxmn.jpg",
          value: 3.8,
        },
        {
          title: "Aladdin",
          img: "https://image.tmdb.org/t/p/original/fhyun1mja3WwQsYr1a3x1x9BttP.jpg",
          value: 3.7,
        },
        {
          title: "The Little Mermaid",
          img: "https://image.tmdb.org/t/p/original/plcZXvI310FkbwIptvd6rqk63LP.jpg",
          value: 4.2,
        },
        {
          title: "Cinderella",
          img: "https://image.tmdb.org/t/p/original/avz6S9HYWs4O8Oe4PenBFNX4uDi.jpg",
          value: 5,
        },
        {
          title: "Alice in Wonderland",
          img: "https://image.tmdb.org/t/p/original/20cvfwfaFqNbe9Fc3VEHJuPRxmn.jpg",
          value: 3.8,
        },
      ],
    };
  },
};
</script>

<style>
.el-row {
  margin-bottom: 20px;
}
.el-row:last-child {
  margin-bottom: 0;
}
.el-col {
  border-radius: 4px;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}
</style>
