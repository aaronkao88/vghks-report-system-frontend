<template>
  <q-card flat bordered class="my-card">
    <q-card-section>
      <div class="text-h6">
        進度明細｜Progress schedule

        <q-btn-dropdown
          id="pg-sd"
          style="color: #21468d; background-color: #f7f9ff"
          label="階段一"
        >
          <q-list>
            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label style="color: #21468d; background-color: #f7f9ff"
                  >階段一</q-item-label
                >
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label style="color: #21468d; background-color: #f7f9ff"
                  >階段二</q-item-label
                >
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label style="color: #21468d; background-color: #f7f9ff"
                  >階段三</q-item-label
                >
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label style="color: #21468d; background-color: #f7f9ff"
                  >階段四</q-item-label
                >
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label style="color: #21468d; background-color: #f7f9ff"
                  >階段五</q-item-label
                >
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </div>
    </q-card-section>
  </q-card>
</template>

<style scoped>
.my-card {
  margin: 45px 0 0 0;
  background-color: #f7f9ff;
  border-radius: 20px 20px 0 0;
  border: none;
}
.my-card-2 {
  height: 480px;
  background-color: #ffffff;
  border-radius: 0 0 20px 20px;
  border: none;
}
.my-card-3 {
  height: 440px;
  background-color: #ffffff;
  border-radius: 0 0 0 20px 0;
  border: none;
}
.text-h6 {
  font-weight: 700;
  color: #21468d;
  margin-left: 40px;
}
.text-allrecevied {
  font-size: 10px;
  margin-top: 24px;
  margin-right: 15px;
  color: #ff5c5c;
}
.q-table__container {
  border: none;
  margin: 20px 0 20px 40px;
}
</style>