<script>
export default {
  name: "CardActions",
  props: {
    date: String,
    action: Function,
  }
};
</script>

<template>
  <div class="actions">
    <p class="actions__text">{{ date }} </p>
    <button class="actions__btn"
            @click="action">
      <svg xmlns="http://www.w3.org/2000/svg"
           width="52"
           height="53"
           viewBox="0 0 52 53"
           fill="none">
        <path d="M23.7714 32.9527L29.7143 26.267L23.7714 19.5813"
              stroke="#292F36"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"/>
      </svg>
    </button>
  </div>
</template>

<style scoped
       lang="scss">

.actions {
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__btn {
    @include rounded(50%);
    background-color: $primary3;
    border: 1px solid #fff;
    outline: none;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
    &:hover {
      background-color: #fff;
    }
  }
}
</style>
