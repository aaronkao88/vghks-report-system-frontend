<template>
  <q-card flat bordered class="my-card">
    <!-- 總覽｜Dashboard -->
    <q-card-section>
      <div class="text-h6">總覽｜Dashboard</div>
    </q-card-section>
  </q-card>

  <!-- 收案總數 -->
  <q-card flat bordered class="my-card-2">
    <q-card-section>
      <div>
        <svg></svg>
      </div>
    </q-card-section>
  </q-card>
</template>

<style scoped>
.my-card {
  margin: 45px 0 0 0;
  background-color: #f7f9ff;
  border-radius: 20px 20px 0 0;
  border: none;
}
.my-card-2 {
  height: 480px;
  background-color: #ffffff;
  border-radius: 0 0 20px 20px;
  border: none;
}
.my-card-3 {
  height: 440px;
  background-color: #ffffff;
  border-radius: 0 0 0 20px 0;
  border: none;
}
.text-h6 {
  font-weight: 700;
  color: #21468d;
  margin-left: 40px;
}
.text-allrecevied {
  font-size: 10px;
  margin-top: 24px;
  margin-right: 15px;
  color: #ff5c5c;
}
.q-table__container {
  border: none;
  margin: 20px 0 20px 40px;
}
</style>

<script>
import * as d3 from "d3";
export default {
  data() {
    return {};
  },
  mounted() {
    const width = 500;
    const height = 450;
    const data = [];

    const svg = d3.select("svg").attr("width", width).attr("height", height);
    const g = svg.append("g");

    //2. Parse the dates
    const parseTime = d3.timeParse("%d-%b-%y");

    //3. Creating the Chart Axes
    const x = d3
      .scaleTime()
      .domain(
        d3.extent(data, function (d) {
          return parseTime(d.date);
        })
      )
      .rangeRound([0, width]);

    const y = d3
      .scaleLinear()
      .domain(
        d3.extent(data, function (d) {
          return d.amount;
        })
      )
      .rangeRound([height, 0]);

    //4. Creating a Line
    const line = d3
      .line()
      .x(function (d) {
        return x(parseTime(d.date));
      })
      .y(function (d) {
        return y(d.amount);
      });

    //5. Appending the Axes to the Chart
    g.append("g")
      .attr("transform", "translate(0," + height + ")")
      .call(d3.axisBottom(x));

    g.append("g")
      .call(d3.axisLeft(y))
      .append("text")
      .attr("fill", "#000")
      .attr("transform", "rotate(-90)")
      .attr("y", 6)
      .attr("dy", "0.71em")
      .attr("text-anchor", "end")
      .text("Price ($)");

    //6. Appending a path to the Chart
    g.append("path")
      .datum(data)
      .attr("fill", "none")
      .attr("stroke", "steelblue")
      .attr("stroke-width", 1.5)
      .attr("d", line);
  },
};
</script> 