<template>
  <div class="container">
    <div class="compare_items">
      <div class="compare_show">
        <div class="compare_show_wrapper">
          <input
            :value="showDifferences"
            @input="$emit('update:showDifferences', $event.target.checked)"
            type="checkbox"
            id="differences"
            name="differences"
          />
          <label for="differences">Показать различия</label>
        </div>
      </div>
      <div
        class="compare_item"
        v-for="(item, index) in selectedItems"
        :key="item"
      >
        <div class="compare_item_card">
          <div class="compare_item_card_img">
            <img :src="require(`../assets/${item.img}`)" alt="phone" />
            <div class="compare_item_card_wrapper">
              <template v-if="item === selectedItem">
                <slot />
              </template>
              <span
                v-if="this.restItems.length > 0"
                class="compare_item_card_icon"
                @click="$emit('select', item, index)"
              >
                <img src="./../assets/arrow_down.svg" alt="arrow_down" />
              </span>
            </div>
          </div>
          <div>{{ item.model }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CompareTableHead",
  props: {
    selectedItems: {
      type: Array,
      required: true,
    },
    restItems: {
      type: Array,
      required: true,
    },
    selectedItem: {
      type: Object,
      required: true,
    },
    showDifferences: {
      type: [Boolean],
      required: true,
    },
  },
  emits: ["update:showDifferences", "select", "showModal"],
};
</script>
<style scoped>
.compare_items {
  padding-top: 20px;
  display: flex;
}
.compare_show {
  width: 25%;
  display: flex;
  align-items: end;
}
.compare_show_wrapper {
  display: flex;
  align-items: center;
}
.compare_show_wrapper > label {
  margin-left: 14px;
  font-weight: 400;
  font-size: 18px;
  letter-spacing: -0.02em;
  color: #0d5adc;
}
.compare_item_card {
  height: 149px;
  display: flex;
  margin-left: 25px;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  font-weight: 500;
  font-size: 18px;
  line-height: 21px;
  color: #3b4157;
  text-align: center;
}
.compare_item_card_img > img {
  height: 120px;
}

.compare_item_card_img {
  position: relative;
  height: 120px;
}

.compare_item {
  display: flex;
  width: 25%;
}

.compare_item_card_icon {
  position: absolute;
  bottom: 26px;
  right: -48px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 30px;
  height: 27px;
  cursor: pointer;
}
.compare_item_card_wrapper {
  position: relative;
}
</style>
