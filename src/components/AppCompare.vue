<template>
  <section class="compare">
    <div class="container">
      <div class="compare_block">
        <div class="compare_title">
          <div class="compare_title_header">Смартфоны</div>
          <div class="compare_title_showed-items">
            Отобразить товары:
            <span class="compare_title_links">
              <a href="2">2</a>
              <a class="underlined" href="3">3</a>
              <a href="4">4</a>
              <a href="5">5</a>
              <a href="6">6</a>
            </span>
          </div>
        </div>
        <CompareTableHead />
        <CompareTableBody />
      </div>
    </div>
  </section>
</template>

<script>
import CompareTableHead from "@/components/CompareTableHead.vue";
import CompareTableBody from "@/components/CompareTableBody.vue";
export default {
  name: "AppCompare",
  components: { CompareTableBody, CompareTableHead },
};
</script>

<style scoped>
.compare {
  padding: 63px 0 91px 0;
}
.compare_title {
  display: flex;
  justify-content: space-between;
}
.compare_title_showed-items,
.compare_title_links a {
  font-weight: 400;
  font-size: 18px;
  line-height: 60px;
  color: #0d5adc;
  letter-spacing: -0.02em;
}
.compare_title_links a {
  margin-left: 3px;
}
.compare_title_header {
  font-weight: 700;
  font-size: 48px;
  line-height: 60px;
  color: #828286;
  letter-spacing: -0.02em;
}
.underlined {
  border-bottom: #0d5adc 1px solid;
}
</style>
