<template>
    <div>
        <div class="row">
            <div class="col-md-12">
                <div class="well">
                    <h2>Create a New Todo</h2>
                    <form>
                        <div class="form-group">
                            <label for="todoitem">Todo Item</label>
                            <input type="text" v-model="input" class="form-control" id="todoitem" placeholder="Todo Item" />
                        </div>
                        <button type="button" v-on:click="add()" class="btn btn-default">Create</button>
                        <button type="button" v-on:click="remove()" class="btn btn-default">Delete</button>
                    </form>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-md-12">
                <h2>List</h2>
                <ul class="list-group">
                    <li v-for="(todo, index) in todos" :key="index" class="list-group-item">
                        {{ index }}: {{ todo }}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Todo",
        data () {
            return {
                todos: [],
                input: ""
            }
        },
        methods: {
            add() {
                this.todos.push(this.input);
                this.input = "";
            },
            remove(){
               this.todos.pop(this.input);
               this.input = "";
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
