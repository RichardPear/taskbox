<template>
  <pure-task-list
    :tasks="tasks"
    @archive-task="archiveTask"
    @pin-task="pinTask"
  ></pure-task-list>
</template>
<script>
import { computed } from "vue";
import { useStore } from "vuex";
import PureTaskList from "./PureTaskList.vue";
export default {
  name: "TaskList",
  components: {
    PureTaskList,
  },
  setup() {
    const store = useStore();
    const tasks = computed(() => store.state.tasks);
    const archiveTask = (task) => store.dispatch("archiveTask", task);
    const pinTask = (task) => store.dispatch("pinTask", task);
    return {
      tasks,
      archiveTask,
      pinTask,
    };
  },
};
</script>
