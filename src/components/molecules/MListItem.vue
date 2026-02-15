<template>
  <li class="m-list-item">
    <div class="m-list-item__segment m-list-item__segment--label">
      <template v-if="props.shouldShowCheckbox">
        <ACheckbox
          :is-checked="props.isCompleted"
          @change="handleChangeCompleted"
        />
      </template>
      <AText
        class="m-list-item__text"
        :class="{ 'm-list-item__text--completed': props.isCompleted }"
        :text="props.text"
      />
    </div>
    <div class="m-list-item__segment">
      <template v-if="props.availableItems?.length">
        <ASelect
          :value="props.selectedItem"
          :options="itemOptions"
          @change="handleChangeItem"
        />
      </template>
      <template v-if="props.shouldShowActionButton">
        TODO Tutaj będzie molekuła MIconButton
      </template>
    </div>
  </li>
</template>
