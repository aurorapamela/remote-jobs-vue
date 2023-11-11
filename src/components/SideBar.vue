<script setup></script>

<template>
  <VNavigation-drawer expand-on-hover rail>
    <VList>
      <VList-item
        prepend-avatar="https://img.freepik.com/psd-premium/cubo-riego-ilustracion-3d_434471-942.jpg?size=626&ext=jpg"
        title="Remote jobs"
        subtitle="Taking the pala"
      ></VList-item>
    </VList>

    <VDivider></VDivider>

    <VList density="compact" nav>
      <VListItem
        prepend-icon="mdi-star"
        title="Starred"
        value="starred"
      ></VListItem>
    </VList>
  </VNavigation-drawer>
</template>
