<template>
  <PureInboxScreen :error="error" />
</template>

<script>
  import { computed } from 'vue';

  import { useStore } from 'vuex';

  import PureInboxScreen from './PureInboxScreen';

  export default {
    name: 'InboxScreen',
    components: { PureInboxScreen },
    setup() {
      const store = useStore();
      const error = computed(() => store.state.error);
      return {
        error,
      };
    },
  };
</script>