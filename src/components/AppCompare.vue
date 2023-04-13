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
        :filteredCharacters="differenceItems"
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
      itemList: [
        {
          id: 1,
          brand: "Apple",
          model: "Apple iPhone 12",
          year: 2020,
          screenSize: 6.1,
          country: "Китай",
          memoryStorage: 128,
          screenUpdateFrequency: 60,
          nfc: false,
          esim: true,
          qiCharge: true,
          price: 81990,
          img: "iphone12.svg",
        },
        {
          id: 2,
          brand: "Xiaomi",
          model: "Xiaomi Mi 11 Lite",
          year: 2021,
          screenSize: 6.55,
          country: "Китай",
          memoryStorage: 128,
          screenUpdateFrequency: 90,
          nfc: true,
          esim: true,
          qiCharge: false,
          price: 27490,
          img: "xiaomi11.svg",
        },
        {
          id: 3,
          brand: "Samsung",
          model: "Samsung Galaxy A72",
          year: 2021,
          screenSize: 6.7,
          country: "Вьетнам",
          memoryStorage: 128,
          screenUpdateFrequency: 90,
          nfc: true,
          esim: false,
          qiCharge: true,
          price: 32890,
          img: "samsunga72.svg",
        },
        {
          id: 4,
          brand: "Apple",
          model: "Apple iPhone Xr",
          year: 2018,
          screenSize: 6.4,
          country: "Китай",
          memoryStorage: 64,
          screenUpdateFrequency: 60,
          nfc: true,
          esim: true,
          qiCharge: true,
          price: 22890,
          img: "iphonexr.svg",
        },
        {
          id: 5,
          brand: "Samsung",
          model: "Samsung Galaxy S21",
          year: 2021,
          screenSize: 6.7,
          country: "Вьетнам",
          memoryStorage: 128,
          screenUpdateFrequency: 90,
          nfc: true,
          esim: false,
          qiCharge: true,
          price: 32890,
          img: "samsunggalaxys21.svg",
        },
        {
          id: 6,
          brand: "Realme",
          model: "Realme 8 Pro",
          year: 2021,
          screenSize: 6.3,
          country: "Китай",
          memoryStorage: 128,
          screenUpdateFrequency: 90,
          nfc: true,
          esim: false,
          qiCharge: true,
          price: 12890,
          img: "realme8pro.svg",
        },
        {
          id: 7,
          brand: "Iphone",
          model: "Iphone X",
          year: 2017,
          screenSize: 6.3,
          country: "Китай",
          memoryStorage: 32,
          screenUpdateFrequency: 60,
          nfc: true,
          esim: false,
          qiCharge: true,
          price: 15890,
          img: "iphonex.png",
        },
      ],
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
      differenceItems: [],
      differenceArray: [
        "brand",
        "year",
        "screenSize",
        "country",
        "memoryStorage",
        "screenUpdateFrequency",
        "nfc",
        "esim",
        "qiCharge",
        "price",
      ],
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
    makeDifferenceItems() {
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
      this.differenceItems = diffCharacteristicsList;
    },
    toggleDifferences() {
      if (this.showDifferences === true) {
        this.makeDifferenceItems();
      } else {
        this.differenceItems = this.differenceArray;
      }
    },
  },
  computed: {
    filteredRestItems() {
      return this.restItems.filter((item) =>
        item.model.toLowerCase().includes(this.filter.toLowerCase())
      );
    },
  },
  created() {
    this.groupItems();
    this.generateItemsPerPage();
    this.differenceItems = this.selectedItems;
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
