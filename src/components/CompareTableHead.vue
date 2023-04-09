<template>
  <div class="compare_items">
    <div class="compare_show">
      <div class="compare_show_wrapper">
        <input type="checkbox" id="differences" name="differences" />
        <label for="differences">Показать различия</label>
      </div>
    </div>
    <div class="compare_item">
      <div class="compare_item_card">
        <div class="compare_item_card_img">
          <img src="./../assets/iphone.svg" alt="phone" />
          <a href="#" class="compare_item_card_icon">
            <img src="./../assets/arrow_down.svg" alt="arrow_down" />
          </a>
        </div>
        <div>Apple iPhone 12</div>
      </div>
    </div>
    <div class="compare_item">
      <div class="compare_item_card">
        <div class="compare_item_card_img">
          <img src="./../assets/xiaomi11.svg" alt="phone" />
          <a href="#" class="compare_item_card_icon">
            <img src="./../assets/arrow_down.svg" alt="arrow_down" />
          </a>
        </div>
        <div>Xiaomi Mi 11 Lite</div>
      </div>
    </div>
    <div class="compare_item">
      <div class="compare_item_card">
        <div class="compare_item_card_img">
          <img src="./../assets/samsunga72.svg" alt="phone" />
          <a href="#" class="compare_item_card_icon">
            <img src="./../assets/arrow_down.svg" alt="arrow_down" />
          </a>
        </div>
        <div>Samsung Galaxy A72</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CompareTableHead",
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
}
.compare_item_card > img {
  height: 120px;
}

.compare_item_card_img {
  position: relative;
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
}

#differences {
  position: relative;
}
#differences::before {
  content: "";
  z-index: -1;
  position: absolute;
  top: -50%;
  left: -50%;
  width: 24px;
  height: 24px;
  background: url(./../assets/Rectangle.svg);
}
</style>
