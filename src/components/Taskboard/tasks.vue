<template>
  <div class="taskboard-tasks">
    <div class="col-3">
      <h3>Sprint Backlog</h3>
      <draggable class="list-group" :list="SprintBacklog" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in SprintBacklog"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>

    <div class="col-3">
      <h3>Todo</h3>
      <draggable class="list-group" :list="Todo" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in Todo"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>
    
    <div class="col-3">
      <h3>In Progress</h3>
      <draggable class="list-group" :list="InProgress" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in InProgress"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>
    
    <div class="col-3">
      <h3>Review</h3>
      <draggable class="list-group" :list="Review" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in Review"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>
    
    <div class="col-3">
      <h3>Ready</h3>
      <draggable class="list-group" :list="Ready" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in Ready"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>

    <div class="col-3">
      <h3>Done</h3>
      <draggable class="list-group" :list="Done" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in Done"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>

    <rawDisplayer class="col-3" :value="list1" title="List 1" />

    <rawDisplayer class="col-3" :value="list2" title="List 2" />
  </div>
</template>
<script>
import draggable from "vuedraggable";
export default {
  name: "two-lists",
  display: "Two Lists",
  order: 1,
  components: {
    draggable
  },
  data() {
    return {
      SprintBacklog: [
        { name: "John", id: 1 },
        { name: "Joao", id: 2 },
        { name: "Jean", id: 3 },
        { name: "Gerard", id: 4 }
      ],
      Todo: [
        { name: "Juan", id: 5 },
        { name: "Edd", id: 6 },
        { name: "Jodsfvsdfhnson", id: 7 }
      ],
      InProgress: [
        { name: "sdfvinJuan", id: 8 },
        { name: "Edgardsdgbon", id: 9 },
        { name: "Johnswergwergon", id: 10 }
      ],
      Review: [
        { name: "Jwwwwuan", id: 11 },
        { name: "Edgarerrrrd", id: 12 },
        { name: "Johnssdfkbvskjfvhon", id: 13 }
      ],
      Ready: [
        { name: "Ju344an", id: 14 },
        { name: "Edga33rd", id: 15 },
        { name: "Johns44on", id: 16 }
      ],
      Done: [
        { name: "Juan", id: 17 },
        { name: "Edgard", id: 18 },
        { name: "Johnson", id: 19 }
      ]
    };
  },
  methods: {
    add: function() {
      this.list.push({ name: "Juan" });
    },
    replace: function() {
      this.list = [{ name: "Edgard" }];
    },
    clone: function(el) {
      return {
        name: el.name + " cloned"
      };
    },
    log: function(evt) {
      window.console.log(evt);
    }
  }
};
</script>

<style scoped>
.col-3 {
    box-shadow: 0px 0px 7px #dadada;
    padding: 5px;
    border-radius: 8px;
    width: 24%;
    display: flex;
    flex-flow: column;
}
.taskboard-tasks {
    display: flex;
}
</style>