<template>
  <div id="bar_chart"></div>
</template>

<script>
import axios from 'axios'
import * as d3 from 'd3'

export default {
  data() {
    return {
      usersBalance: [],
      userActions: [],
      svg: null,
      x: null,
      y: null,
      Tooltip: null,
    }
  },
  computed: {
    margin() {
      return { top: 100, right: 100, bottom: 100, left: 100 };
    },
    width() {
      return 1300 - this.margin.left - this.margin.right;
    },
    height() {
      return 400 - this.margin.top - this.margin.bottom;
    },
  },
  mounted() {
    this.getUsersBalance();
  },
  methods: {
    getUsersBalance() {
      axios.get("getUsersBalance").then(response => {
        this.usersBalance = response.data;
        this.createChart();
      }).catch(error => {
        console.error(error);
      })
    },
    getUserActions(user_id) {
      axios.get("getUserActions", { params: { user_id: user_id } }).then(response => {
        this.userActions = response.data;
      }).catch(error => {
        console.error(error);
      })
    },
    createChart() {
      // your d3 code here
    }
  }
}
</script>

<style scoped>
div.tooltip {
  position: absolute;
  padding: 10px;
  font: 12px sans-serif;
  background: lightsteelblue;
  border: 0px;
  border-radius: 8px;
  pointer-events: none;
  align-items: left;
}
</style>
