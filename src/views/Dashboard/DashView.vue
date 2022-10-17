<template>
  <div class="q-pa-md">
    <div class="row justify-center">
      <div class="col-9">
        <DashView></DashView>

        <div class="col-9">
          <PS></PS>
        </div>
        <div class="col-4">
          <allcase></allcase>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import DashView from "@/components/Dashboard/MyCard.vue";
import PS from "@/components/Dashboard/ProGress.vue";
import allcase from "@/components/Dashboard/AllCase.vue";

export default {
  components: {
    DashView,
    PS,
    allcase,
  },
};
</script>