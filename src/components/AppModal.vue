<template>
  <div class="modal">
    <div class="modal_wrapper">
      <input
        v-if="restItems.length > 3"
        :value="filter"
        @input="$emit('update:filter', $event.target.value)"
        type="text"
        name="filter"
        placeholder="Поиск"
      />
      <div class="modal_items">
        <div
          class="modal_item"
          v-for="(item, index) in filteredRestItems"
          :key="item.id"
        >
          <div class="modal_item_img">
            <span @click="$emit('change', item, index)">
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M19.0909 4.54548H3.10384L6.09735 1.55191C6.45238 1.19694 6.45238 0.621302 6.09735 0.266272C5.74239 -0.0887575 5.16675 -0.0887575 4.81172 0.266272L0.266272 4.81172C-0.0887575 5.16669 -0.0887575 5.74233 0.266272 6.09735L4.81172 10.6428C4.98923 10.8203 5.2219 10.9091 5.45457 10.9091C5.68723 10.9091 5.9199 10.8203 6.09735 10.6428C6.45238 10.2878 6.45238 9.7122 6.09735 9.35717L3.10384 6.36366H19.0909C19.593 6.36366 20 5.95663 20 5.45457C20 4.95251 19.593 4.54548 19.0909 4.54548Z"
                  fill="#36935B"
                />
                <path
                  d="M15.1883 9.35717C14.8333 9.0022 14.2576 9.0022 13.9026 9.35717C13.5476 9.71214 13.5476 10.2878 13.9026 10.6428L16.8962 13.6364H0.90912C0.40706 13.6364 3.02863e-05 14.0434 3.02863e-05 14.5455C3.02863e-05 15.0475 0.40706 15.4546 0.90912 15.4546H16.8962L13.9027 18.4481C13.5476 18.8031 13.5476 19.3787 13.9027 19.7338C14.0801 19.9112 14.3128 20 14.5455 20C14.7781 20 15.0108 19.9112 15.1883 19.7337L19.7337 15.1883C20.0887 14.8333 20.0887 14.2576 19.7337 13.9026L15.1883 9.35717Z"
                  fill="#36935B"
                />
              </svg>
            </span>
            <div class="modal_item_img_wrapper">
              <img :src="require(`../assets/${item.img}`)" alt="phone" />
            </div>
          </div>
          <div class="modal_item_text">{{ item.model }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppModal",
  props: {
    restItems: {
      type: Array,
      required: true,
    },
    filteredRestItems: {
      type: Array,
      required: true,
    },
    filter: {
      type: String,
    },
  },
  emits: ["update:filter", "change"],
};
</script>

<style scoped>
/* .modal_overlay {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
} */
.modal {
  position: absolute;
  z-index: 100;
  left: 79px;
  top: -57px;
  width: 421px;
  padding: 34px 9px 25px 18px;
  border: 1px solid #e3e3e3;
  box-shadow: 0px 16px 32px rgba(35, 39, 51, 0.1);
  border-radius: 4px;
  background: #ffffff;
}
.modal input {
  display: block;
  width: 364px;
  height: 47px;
  border: 1px solid #c1c1c1;
  border-radius: 4px;
  padding: 10px 37px 9px 16px;
  font-weight: 400;
  font-size: 24px;
  line-height: 28px;
  color: #c1c1c1;
  margin-bottom: 18px;
}
.modal_wrapper::-webkit-scrollbar {
  width: 6px;
  background: none;
}
.modal_wrapper::-webkit-scrollbar-thumb {
  background: #e3e3e3;
  border-radius: 8px;
}
.modal_wrapper {
  max-height: 280px;
  overflow-y: auto;
}
.modal_item {
  display: flex;
  align-items: center;
  margin-bottom: 30px;
}
.modal_item:last-child {
  margin-bottom: 0px;
}
.modal_item_text {
  margin-left: 18px;
}
.modal_item_img {
  display: flex;
  width: 66px;
  align-items: center;
  justify-content: space-between;
}
.modal_item_img_wrapper {
  width: 40px;
  display: flex;
  justify-content: center;
}
.modal_item_img img {
  height: 50px;
}
</style>
