<template>
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
</template>

<script>
export default {
  name: "CompareTableBody",
};
</script>

<style scoped>
.compare_table {
  background-color: #f4f9fc;
  margin-top: 77px;
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
</style>
