<template>
  <div class="row justify-start">
    <div class="col">
      <q-card flat bordered class="my-card-3">
        <q-card-section>
          <div class="text-h6">
            收案總數
            <q-btn-dropdown
              id="pg-sd"
              style="color: #21468d; background-color: #f7f9ff"
              label="時間"
            >
              <q-list>
                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label
                      style="color: #21468d; background-color: #f7f9ff"
                      >時間</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label
                      style="color: #21468d; background-color: #f7f9ff"
                      >未處理</q-item-label
                    >
                  </q-item-section>
                </q-item>
              </q-list>
            </q-btn-dropdown>
          </div>

          <!-- 收案總數資料 -->
          <q-table
            :dense="$q.screen.lt.md"
            :rows="rows"
            :columns="columns"
            row-key="name"
            title-class="text-bold text-blue-9"
            table-style="background-color: #F7F9FF; color: #21468D;"
            table-header-style="height: 65px; background-color: #D3DEFF; color: #21468D;"
          />

          <div class="text-allrecevied absolute-right">共計：118筆資料</div>
        </q-card-section>
      </q-card>
    </div>

    <!-- 等待檢驗資料 -->
    <div class="col">
      <q-card flat bordered class="my-card-3">
        <q-card-section>
          <div class="case_recevied">
            <div class="text-h6">等待檢驗資料</div>

            <!-- 收案總數資料 -->
            <q-table
              :dense="$q.screen.lt.md"
              :rows="rows"
              :columns="columns"
              row-key="name"
              title-class="text-bold text-blue-9"
              table-style="background-color: #F7F9FF; color: #21468D;"
              table-header-style="height: 65px; background-color: #D3DEFF; color: #21468D;"
            />

            <div class="text-allrecevied absolute-right">共計：25筆資料</div>
          </div>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<style scoped>
.my-card {
  margin: 45px 0 0 0;
  background-color: #f7f9ff;
  font-weight: 700;
  border: none;
}
.my-card-2 {
  height: 480px;
  background-color: #ffffff;
  font-weight: 700;
  border: none;
}
.my-card-3 {
  height: 440px;
  background-color: #ffffff;
  font-weight: 700;
  border: none;
}
.text-h6 {
  font-weight: 700;
  color: #21468d;
  margin-left: 40px;
}
.text-allrecevied {
  font-weight: 700;
  font-size: 10px;
  margin-top: 24px;
  margin-right: 15px;
  color: #ff5c5c;
}

.q-table__container {
  border: none;
  margin: 20px 0 20px 40px !important;
}
</style>

<script>
const columns = [
  {
    number: "number",
    label: "編號",
    require: true,
    field: (row) => row.number,
  },
  { name: "name", label: "編號", require: true, field: (row) => row.name },
  {
    gender: "gender",
    label: "性別",
    require: true,
    field: (row) => row.gender,
  },
  {
    identify: "identify",
    label: "身分證字號",
    require: true,
    field: (row) => row.identify,
  },
  {
    medicalnumber: "medicalnumber",
    label: "病歷號",
    require: true,
    field: (row) => row.medicalnumber,
  },
  {
    nstatusame: "status",
    label: "狀態",
    require: true,
    field: (row) => row.status,
  },
];

const rows = [
  {
    number: "1",
    name: "王大明",
    gender: "男",
    birth: "1995/04/02",
    identify: "A123456789",
    medicalnumber: "540324",
    status: "階段一22/08/30",
  },
  {
    number: "2",
    name: "王大明",
    gender: "男",
    birth: "1995/04/02",
    identify: "A123456789",
    medicalnumber: "540324",
    status: "階段一22/08/30",
  },
  {
    number: "3",
    name: "王大明",
    gender: "男",
    birth: "1995/04/02",
    identify: "A123456789",
    medicalnumber: "540324",
    status: "階段一22/08/30",
  },
  {
    number: "4",
    name: "王大明",
    gender: "男",
    birth: "1995/04/02",
    identify: "A123456789",
    medicalnumber: "540324",
    status: "階段一22/08/30",
  },
  {
    number: "5",
    name: "王大明",
    gender: "男",
    birth: "1995/04/02",
    identify: "A123456789",
    medicalnumber: "540324",
    status: "階段一22/08/30",
  },
];

export default {
  setup() {
    return {
      onItemClick() {},
      columns,
      rows,
    };
  },
};
</script>