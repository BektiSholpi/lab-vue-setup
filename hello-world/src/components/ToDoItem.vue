<template>
  <div>
    <h1>Hola</h1>
    <h1>{{ 2 + 2 }}</h1>
    <h1>Tiene que salir el mismo numero {{ addNum() }}</h1>
    <h1>{{ myName() }}</h1>

    <h1 v-show="showElement">
      Si ves abajo otro texto entonces es "true" si no lo ves es "false"
    </h1>
    <h1 v-if="showElement">Esto me referia...</h1>

    <div v-for="(book, index) in myFavBook" :key="index">
      <ul>
        <li>
          <h1>Post Title: {{ book.title }}</h1>
          <h4>Post description: {{ book.description }}</h4>
          <p>Post Content: {{ book.content }}</p>
        </li>
      </ul>
    </div>

    <div v-for="(btn, index) in buttonCheckAge" :key="index" class="select-age">
      <div>
        <p>{{ btn.btnName }}</p>
      </div>
      <div>
        <button
          :class="[btn.className, { selected: selectedIndex === index }]"
          @click="selectedIndex = index"
        >
          {{ btn.btnText }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToDoItem",
  /* data */
  data() {
    return {
      showElement: false,

      myFavBook: [
        {
          title: "Memoirs of a Geisha",
          description: "una novela de Arthur Golden",
          content: "con que luego Steven Spielberg ha hecho una pelicula",
        },
        {
          title: "Harry Poter",
          description: "un libro interesante",
          content: "que nunca he leido",
        },
      ],
      selectedIndex: -1,
      buttonCheckAge: [
        {
          btnName: "Blue",
          btnText: "btn-Blue",
          className: "btn-teens",
          state: 0,
        },
        {
          btnName: "Red",
          btnText: "btn-Red",
          className: "btn-minxes",
          state: 1,
        },
        {
          btnName: "Green",
          btnText: "btn-Green",
          className: "btn-milfs",
          state: 2,
        },
      ],
    };
  },
  methods: {
    addNum() {
      return 2 + 2;
    },
    myName() {
      return "Sholpi";
    },
    color() {
      this.buttonColor;
    },
  },
};
</script>

<style scoped>
.selected.btn-teens {
  background: #00f;
  color: #fff;
}

.selected.btn-minxes {
  background: #f00;
  color: #eee;
}

.selected.btn-milfs {
  background: #0f0;
  color: #000;
}
</style>
