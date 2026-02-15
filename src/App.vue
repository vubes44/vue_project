<template>
  <div id="app">
    <MStatusFilter
      :status-options="[
        { value: 'all', label: 'All' },
        { value: 'active', label: 'Active' },
        { value: 'inactive', label: 'Inactive' },
      ]"
      selected-status="active"
      @status-change="handleStatusChange"
    />
    <MColorFilter
      :available-colors="['red', 'green', 'blue']"
      :selected-colors="['red']"
      @change-color="handleColorChange"
    />
  </div>
</template>

<script setup lang="ts">
  import MStatusFilter from "@molecules/MStatusFilter.vue";
  import MColorFilter from "@molecules/MColorFilter.vue";

  const handleStatusChange = (status: string) => {
    console.log("Status changed to:", status);
  };

  const handleColorChange = (color: string, action: "added" | "removed") => {
    console.log("Color changed:", color, action);
  };
</script>
