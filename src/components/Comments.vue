<template>
  <div id="app" class="container">
    <h1>Comment System</h1>
    <hr />
    <div class="form-todo form-group">
      <p>
        <input
          placeholder="nome"
          type="text"
          name="author"
          class="form-control"
          v-model="autor"
        />
      </p>
      <p>
        <textarea
          placeholder="comentário"
          name="messge"
          class="form-control"
          v-model="comentario"
        ></textarea>
      </p>
      <button v-on:click="addComment" type="submit" class="btn-primary">
        Comentar
      </button>
      <p v-if="comments.length <=0">Sem comentário</p>
      <hr />
    </div>
    <div class="list-group">
      <div class="list-group-item" v-for="(comment, index) in comments" :key="index">
        <span class="comment_author"
          >Autor: <strong>{{ comment.name }}</strong></span
        >
        <p>{{ comment.messege }}</p>
        <div>
          <button
            typr="submit"
            class="btn-danger"
            v-on:click="reComment(index)"
          >
            Excluir
          </button>
        </div>
      </div>
    </div>
    <hr>/
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      comments: [],
      autor: "",
      comentario: "",
    };
  },
  methods: {
    addComment() {
      if (this.autor.trim() == "" || this.comentario.trim() == "") {
        return;
      }
      this.comments.push({
        name: this.autor,
        messege: this.comentario,
      });

      this.autor = "";
      this.comentario = "";
    },
    reComment(index) {
      this.comments.pop(index);
      //this.comments.splice(index,1);
    },
  },
};
</script>

<style scoped>
</style>