<template>
  <AButton
    :isDisabled="props.isDisabled"
    @click="handleClick"
    class="m-icon-button"
    :class="{
      'm-icon-button--disabled': props.isDisabled,
    }"
  >
    <AIcon
      :icon="props.icon"
      alt="icon"
    />
  </AButton>
</template>

<script setup lang="ts">
  import AButton from "@atoms/AButton.vue";
  import AIcon from "@atoms/AIcon.vue";

    const props = withDefaults(
        defineProps<{
            icon: string;
            alt: string;
            isDisabled?: boolean;
        }>(),
        {
            isDisabled: false,
        }
    );

  const emit = defineEmits<{
    (e: "click"): void;
  }>();

  const handleClick = () => {
    if (props.isDisabled) return;
    emit("click");
  };

</script>
<style scoped lang="scss">
    .m-icon-button {
        padding: 5px;
        background-color: transparent;
        border: none;
        cursor: pointer;
        opacity: 0.7;
        transition: opacity 0.2s;
    
        &:hover {
        opacity: 1;
        }
    
        &--disabled {
        opacity: 0.2;
        cursor: auto;
    }
  }