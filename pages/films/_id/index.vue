<template>
  <div style="padding: 20px 160px">
    <el-row :gutter="20">
      <el-col :span="16"
        ><div class="grid-content bg-purple">
          <el-row :gutter="20">
            <el-col :span="8"
              ><div class="grid-content bg-purple">
                <img
                  src="https://image.tmdb.org/t/p/original/qNBAXBIQlnOThrVvA6mA2B5ggV6.jpg"
                  alt="mario"
                  style="width: 100%; border-radius: 16px"
                /></div
            ></el-col>
            <el-col :span="14"
              ><div class="grid-content bg-purple">
                <h1>The Super Mario Bros. Movie</h1>
                <div class="films_info">
                  <div class="tag-group" style="margin-bottom: 12px">
                    <span class="tag-group__title" style="margin-right: 12px"
                      ><strong>Genres:</strong></span
                    >
                    <el-tag
                      v-for="item in items"
                      :key="item.label"
                      :type="item.type"
                      effect="dark"
                      style="margin-right: 5px; border-radius: 16px"
                    >
                      {{ item.label }}
                    </el-tag>
                  </div>
                  <div class="tag-group" style="margin-bottom: 12px">
                    <span class="tag-group__title" style="margin-right: 12px"
                      ><strong>Release date:</strong></span
                    >
                    <span>05/04/2023</span>
                  </div>
                  <div class="tag-group" style="margin-bottom: 12px">
                    <span class="tag-group__title" style="margin-right: 12px"
                      ><strong>Runtime:</strong></span
                    >
                    <span>92 minutes</span>
                  </div>
                  <div class="tag-group" style="margin-bottom: 12px">
                    <span class="tag-group__title" style="margin-right: 12px"
                      >While working underground to fix a water main, Brooklyn
                      plumbers—and brothers—Mario and Luigi are transported down
                      a mysterious pipe and wander into a magical new world. But
                      when the brothers are separated, Mario embarks on an epic
                      quest to find Luigi. Rated 7.503 stars out of 10
                    </span>
                  </div>
                  <div class="tag-group" style="margin-bottom: 12px">
                    <el-rate
                      v-model="value"
                      disabled
                      show-score
                      text-color="#ff9900"
                      score-template="{value} points"
                    >
                    </el-rate>
                  </div>
                  <div class="tag-group" style="margin-bottom: 12px">
                    <el-row>
                      <el-button type="success" round
                        >WATCH NOW
                        <font-awesome-icon
                          :icon="['fass', 'circle-play']"
                          style="margin-left: 5px"
                      /></el-button>
                      <el-button type="danger" round
                        >WATCH TRAILER
                        <font-awesome-icon
                          :icon="['fas', 'film']"
                          style="margin-left: 5px"
                        />
                      </el-button>
                    </el-row>
                  </div>
                </div></div
            ></el-col>
          </el-row></div
      ></el-col>
      <el-col :span="3"> </el-col>
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
                    <img :src="film.img" alt="mario" style="width: 100%; border-radius: 6px;" /></div
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

    <div class="main_actor_list">
      <TitleList content="Main actor" />
      <div class="main_actors">
        <el-row
          :gutter="20"
          style="display: flex; justify-content: space-around"
        >
          <el-col :span="4" v-for="(actor, index) in mainActors" :key="index"
            ><div class="grid-content main_actor">
              <div class="demo-basic--circle">
                <div class="block">
                  <el-avatar :size="150" :src="actor.img"></el-avatar>
                </div>
              </div>
              <p>{{ actor.name }}r</p>
              <p>
                <strong>{{ actor.character }}</strong>
              </p>
            </div></el-col
          >
        </el-row>
      </div>
    </div>

    <div style="">
      <TitleList content="Films Top" />
      <CardSlider />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { type: "", label: "Tag 1" },
        { type: "", label: "Tag 2" },
        { type: "", label: "Tag 3" },
        { type: "", label: "Tag 4" },
        { type: "", label: "Tag 5" },
      ],
      value: 3.7,
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
      mainActors: [
        {
          name: "Scott Weinger",
          character: "Aladdin (voice)",
          img: "https://www.cameo.com/cdn-cgi/image/fit=cover,format=auto,width=500,height=500/https://cdn.cameo.com/resizer/NuOC-RE9O_avatar-TANsNQE2w.jpg",
        },
        {
          name: "Linda Larkin",
          character: "Jasmine (voice)",
          img: "https://the-avocado.org/wp-content/uploads/2018/01/linda-larkin-2.96.jpg",
        },
        {
          name: "Robin Williams",
          character: "Genie / Peddler (voice)",
          img: "https://images6.fanpop.com/image/photos/40600000/Robin-Williams-robin-williams-40671020-2151-3000.jpg",
        },
        {
          name: "Jonathan Freeman",
          character: "Jafar (voice)",
          img: "https://www.cameo.com/cdn-cgi/image/fit=cover,format=auto,width=500,height=500/https://cdn.cameo.com/resizer/NuOC-RE9O_avatar-TANsNQE2w.jpg",
        },
        {
          name: "Gilbert Gottfried",
          character: "Iago (voice)",
          img: "https://www.cameo.com/cdn-cgi/image/fit=cover,format=auto,width=500,height=500/https://cdn.cameo.com/resizer/NuOC-RE9O_avatar-TANsNQE2w.jpg",
        },
        {
          name: "Gilbert Gottfried",
          character: "Sultan (voice)",
          img: "https://www.cameo.com/cdn-cgi/image/fit=cover,format=auto,width=500,height=500/https://cdn.cameo.com/resizer/NuOC-RE9O_avatar-TANsNQE2w.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.main_actors {
  margin-top: 30px;
}
.main_actor {
  display: flex;
  flex-direction: column;
  align-items: center;
}
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
