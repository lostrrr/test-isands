<template>
  <section class="compare">
    <div class="container">
      <div class="compare_block">
        <div class="compare_title">
          <div class="compare_title_header">Смартфоны</div>
          <div class="compare_title_showed-items">
            Отобразить товары:
            <span class="compare_title_links">
              <span
                v-for="p in itemsPerPage"
                :key="p"
                @click="selectItemsPerPage(p)"
                :class="{
                  underlined: showedItems === p,
                }"
                class="compare_title_link"
                >{{ p }}</span
              >
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
  props: {
    itemList: {
      type: Array,
    },
  },
  data() {
    return {
      itemsPerPage: [2, 3, 4, 5, 6],
      showDifferences: false,
      showedItems: 3,
    };
  },
  methods: {
    selectItemsPerPage(items) {
      this.showedItems = items;
    },
  },
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
.compare_title_link {
  font-weight: 400;
  font-size: 18px;
  line-height: 60px;
  color: #0d5adc;
  letter-spacing: -0.02em;
}
.compare_title_link {
  margin-left: 3px;
  cursor: pointer;
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
