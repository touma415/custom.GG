<template>
  <div class="wrapper">
    <div class="main-contents">
      <input type="text" placeholder="id" v-model="matchID" />
      <button v-on:click="getMatch(matchID)">show</button>
    </div>
  </div>
</template>

<script>
//=================
//どうやらカスタムはplayerNameが取れないらしい　いやまぁわかるけど
//人力入力でなんとかするのはアリだけど手間かかると結局やらんよね
//う～ん　悩ましい
//=================

// import Vue from "vue";
import axios from "axios";

export default {
  props: {
    isActive: {
      type: Number,
      default: 1
    }
  },

  components: {},

  data() {
    return {
      matchid: "211279525",
      apikey: "RGAPI-0c6e7e7d-a260-471e-83c3-db269e8c3911",
      matchurl: "https://jp1.api.riotgames.com/lol/match/v4/matches/",
      CORS_PROXY: "https://cors-anywhere.herokuapp.com/",
      matches: []
    };
  },
  methods: {
    tabChange(num) {
      this.isActive = num;
    },
    getMatch() {
      const url =
        this.CORS_PROXY +
        this.matchurl +
        this.matchid +
        "?api_key=" +
        this.apikey;
      axios.get(url).then(res => {
        console.log(res.data);
        this.matches.push(res);
        // console.log(this.matches);
      });
    },
    matchDataPerse(data) {
      const duration = data.duration;
      if (data.gameType == "MATCH_GAME") {
        const type = nomal;
      }
      data.participantIdentities.forEach(player => {
        const sumonerName = player.sumonerName;
      });
    }
  },
  created: function() {
    this.getMatch();
  }
};
</script>