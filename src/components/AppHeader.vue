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
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style>
header {
  height: 101px;
  background: #ffffff;
  border-bottom: 1px solid #a6a5a9;
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
</style>
