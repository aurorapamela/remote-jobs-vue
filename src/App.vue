<script setup>
import SideBar from "./components/SideBar.vue";
import Cards from "./components/Cards.vue";
import { listOfRemotesJobs } from "./data.js";

const data = () => listOfRemotesJobs;

// export default {
//   components: {
//     Cards,
//     SideBar,
//   },
//   data() {
//     return {
//       listOfRemotesJobs,
//     };
//   },
// };
</script>

<template>
  <VApp>
    <!-- Sidebar -->
    <SideBar></SideBar>
    <VMain>
      <VRow class="px-1">
        <VCol
          v-for="job in listOfRemotesJobs"
          :key="job.id"
          cols="12"
          md="4"
          lg="3"
          xl="2"
        >
          <!-- Cards -->
          <Cards :job="job"></Cards>
        </VCol>
      </VRow>
    </VMain>
  </VApp>
</template>
