<template>
  <section class="compare">
    <div class="compare_block">
      <div class="container">
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
                  underlined: numberOfShowedItems === p,
                }"
                class="compare_title_link"
                >{{ p }}</span
              >
            </span>
          </div>
        </div>
      </div>
      <CompareTableHead
        :selectedItems="selectedItems"
        :restItems="restItems"
        :selectedItem="selectedItem"
        v-model:showDifferences="showDifferences"
        @select="select"
      >
        <AppModal
          v-if="showModal"
          @close="showModal = false"
          v-model:filter="filter"
          :filteredRestItems="filteredRestItems"
          :restItems="restItems"
          @change="change"
      /></CompareTableHead>
      <CompareTableBody
        :selectedItems="selectedItems"
        :rows="rows"
        :filteredCharacters="filteredCharacters"
      />
    </div>
  </section>
</template>

<script>
import CompareTableHead from "@/components/CompareTableHead.vue";
import CompareTableBody from "@/components/CompareTableBody.vue";
import AppModal from "./AppModal.vue";
export default {
  name: "AppCompare",
  components: { CompareTableBody, CompareTableHead, AppModal },
  data() {
    return {
      rows: [
        { prop: "brand", title: "Производитель" },
        { prop: "year", title: "год релиза" },
        { prop: "screenSize", title: "Диагональ экрана (дюйм)" },
        { prop: "country", title: "Страна-производитель" },
        { prop: "memoryStorage", title: "Объем памяти" },
        { prop: "screenUpdateFrequency", title: "Частота обновления экрана" },
        { prop: "nfc", title: "NFC" },
        { prop: "esim", title: "Поддержка eSIM" },
        { prop: "qiCharge", title: "Поддержка беспроводной зарядки" },
        { prop: "price", title: "Стоимость" },
      ],
      itemsPerPage: [],
      showDifferences: false,
      numberOfShowedItems: 3,
      selectedItems: [],
      selectedItem: {},
      selectedItemIndex: null,
      restItems: [],
      changedItem: {},
      showModal: false,
      filter: "",
      filteredCharacters: [],
    };
  },
  methods: {
    selectItemsPerPage(items) {
      this.numberOfShowedItems = items;
      this.groupItems();
    },
    groupItems() {
      this.selectedItems = this.itemList.filter(
        ({ id }) => id <= this.numberOfShowedItems
      );
      this.restItems = this.itemList.filter(
        ({ id }) => id > this.numberOfShowedItems
      );
    },
    select(item, index) {
      this.selectedItem = item;
      this.selectedItemIndex = index;
      this.showModal = true;
    },
    change(item, index) {
      this.selectedItems.splice(this.selectedItemIndex, 1, item);
      this.restItems.splice(index, 1, this.selectedItem);
      this.selectedItem = item;
    },
    generateItemsPerPage(length = 6) {
      if (this.itemList.length < 6) {
        length = this.itemList.length;
      }
      this.itemsPerPage = [...Array(length + 1).keys()].slice(2);
    },
    makeFilteredCharacters() {
      const diffCharacteristicsList = [];
      for (const key in this.selectedItems[0]) {
        let identicalKeysValue = true;
        this.selectedItems.forEach((item) => {
          if (!identicalKeysValue) return;
          identicalKeysValue = item[key] === this.selectedItems[0][key];
        });
        if (identicalKeysValue) continue;
        diffCharacteristicsList.push(key);
      }
      this.filteredCharacters = diffCharacteristicsList;
    },
    toggleDifferences() {
      if (this.showDifferences === true) {
        this.makeFilteredCharacters();
      } else {
        this.filteredCharacters = this.differenceArray;
      }
    },
  },
  computed: {
    itemList() {
      return this.$store.state.itemList;
    },
    filteredRestItems() {
      return this.restItems.filter((item) =>
        item.model.toLowerCase().includes(this.filter.toLowerCase())
      );
    },
    differenceArray() {
      return this.rows.map(({ prop }) => prop);
    },
  },
  created() {
    this.groupItems();
    this.generateItemsPerPage();
    this.filteredCharacters = this.selectedItems;
  },
  watch: {
    itemList() {
      this.generateItemsPerPage();
    },
    showDifferences() {
      this.toggleDifferences();
    },
    selectedItems() {
      this.toggleDifferences();
    },
  },
};
</script>

<style scoped>
.compare {
  padding: 63px 0 0px 0;
}
.compare_title {
  display: flex;
  justify-content: space-between;
}
.compare_title_showed-items {
  display: flex;
  align-items: center;
}
.compare_title_showed-items,
.compare_title_link {
  font-weight: 400;
  font-size: 18px;
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
