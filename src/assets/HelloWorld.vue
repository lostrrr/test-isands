<template>
  <header>
    <nav>
      <div class="container">
        <div class="menu">
          <div class="menu_catalog">
            <a href="#" class="menu_link">Каталог</a>
          </div>
          <div class="menu_user">
            <div class="menu_compare">
              <a href="#" class="menu_link">Сравнение</a>
            </div>
            <div class="menu_user_profile">
              <a href="#" class="menu_link">Личный кабинет</a>
              <a href="#" class="menu_link">
                <svg
                  width="20"
                  height="21"
                  viewBox="0 0 20 21"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M17.0712 2.93137C15.1824 1.04106 12.6711 0 10.0001 0C7.32884 0 4.81769 1.04106 2.92894 2.93137C1.0402 4.82167 0 7.33491 0 10.0083C0 12.6816 1.0402 15.195 2.92894 17.0853C4.81769 18.9756 7.32884 20.0167 10.0001 20.0167C12.6711 20.0167 15.1824 18.9756 17.0712 17.0853C18.9599 15.195 20.0001 12.6816 20.0001 10.0083C20.0001 7.33491 18.9599 4.82167 17.0712 2.93137ZM5.01331 17.2951C5.43155 14.885 7.51836 13.1072 10.0001 13.1072C12.4819 13.1072 14.5686 14.885 14.9868 17.2951C13.567 18.2714 11.8491 18.8438 10.0001 18.8438C8.15099 18.8438 6.43314 18.2714 5.01331 17.2951ZM6.82042 8.7521C6.82042 6.99725 8.24682 5.56983 10.0001 5.56983C11.7533 5.56983 13.1797 6.99741 13.1797 8.7521C13.1797 10.5068 11.7533 11.9344 10.0001 11.9344C8.24682 11.9344 6.82042 10.5068 6.82042 8.7521ZM16.0018 16.4816C15.6864 15.3596 15.0601 14.3416 14.1821 13.5464C13.6434 13.0585 13.0303 12.6735 12.3711 12.4021C13.5626 11.6244 14.3517 10.2788 14.3517 8.7521C14.3517 6.35066 12.3995 4.39697 10.0001 4.39697C7.6006 4.39697 5.64853 6.35066 5.64853 8.7521C5.64853 10.2788 6.43772 11.6244 7.62898 12.4021C6.96995 12.6735 6.3567 13.0584 5.81806 13.5463C4.94022 14.3415 4.31369 15.3595 3.99828 16.4815C2.26106 14.8668 1.17188 12.5626 1.17188 10.0083C1.17188 5.13642 5.13217 1.17285 10.0001 1.17285C14.8679 1.17285 18.8282 5.13642 18.8282 10.0083C18.8282 12.5628 17.7391 14.867 16.0018 16.4816Z"
                    fill="#3B4157"
                  />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </header>
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
        <div class="compare_table">
          <table class="compare_table_table">
            <tbody>
              <tr class="compare_table_tr">
                <td class="compare_table_title">Производитель</td>
                <td>Apple</td>
                <td>Xiaomi</td>
                <td>Samsung</td>
              </tr>
              <tr class="compare_table_tr">
                <td class="compare_table_title">NFC</td>
                <td>
                  <svg
                    width="22"
                    height="22"
                    viewBox="0 0 22 22"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M11 22C17.0751 22 22 17.0751 22 11C22 4.92487 17.0751 0 11 0C4.92487 0 0 4.92487 0 11C0 17.0751 4.92487 22 11 22ZM8.75981 11.0304L4 15.7888L6.2734 18.0629L11.0338 13.3038L15.7266 17.9952L18 15.7211L13.3079 11.0304L17.9979 6.34168L15.7245 4.06764L11.0338 8.75697L6.27549 3.99996L4.00209 6.274L8.75981 11.0304Z"
                      fill="#EF4058"
                    />
                  </svg>
                </td>
                <td>
                  <svg
                    width="22"
                    height="22"
                    viewBox="0 0 22 22"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M22 11C22 17.0751 17.0751 22 11 22C4.92487 22 0 17.0751 0 11C0 4.92487 4.92487 0 11 0C17.0751 0 22 4.92487 22 11ZM9.01982 12.9508L16.7961 5.17451L18.7334 7.11161L9.01982 16.8255L3.2667 11.0722L5.20408 9.13514L9.01982 12.9508Z"
                      fill="#36935B"
                    />
                  </svg>
                </td>
                <td>
                  <svg
                    width="22"
                    height="22"
                    viewBox="0 0 22 22"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M22 11C22 17.0751 17.0751 22 11 22C4.92487 22 0 17.0751 0 11C0 4.92487 4.92487 0 11 0C17.0751 0 22 4.92487 22 11ZM9.01982 12.9508L16.7961 5.17451L18.7334 7.11161L9.01982 16.8255L3.2667 11.0722L5.20408 9.13514L9.01982 12.9508Z"
                      fill="#36935B"
                    />
                  </svg>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
a {
  text-decoration: none;
}
header {
  height: 101px;
  background: #ffffff;
  border: 1px solid #a6a5a9;
}
.container {
  width: 1100px;
  margin: 0 auto;
}
nav {
  height: 101px;
}
.menu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 101px;
}
.menu_user {
  display: flex;
  width: 255px;
  justify-content: space-between;
  align-items: center;
}
.menu_user_profile {
  width: 137px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.menu_user_profile a {
  font-weight: 900;
  font-size: 12px;
  color: #3b4157;
}
.menu_compare a {
  font-weight: 900;
  font-size: 12px;
  text-transform: uppercase;
  line-height: 14px;
  letter-spacing: -0.02em;
  color: #3b4157;
}
.menu_catalog a {
  font-weight: 900;
  font-size: 18px;
  color: #0d5adc;
  line-height: 21px;
  letter-spacing: -0.05em;
}
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
.compare_table {
  background-color: #f4f9fc;
  margin-top: 77px;
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
.compare_table_tr {
  min-height: 89px;
  display: flex;
  align-items: center;
  font-weight: 500;
  font-size: 18px;
  color: #3b4157;
  border-top: 1px solid #cdcfd2;
}
.compare_table td {
  width: 25%;
}
.compare_table td :not(:first-child) {
  padding-left: 10px;
}

.compare_table_table {
  width: 100%;
}
.compare_table_title {
  font-weight: 500;
  font-size: 18px;
  text-transform: uppercase;
  color: #a4a9b9;
}
.underlined {
  border-bottom: #0d5adc 1px solid;
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
