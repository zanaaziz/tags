<template>
        <form>
            <div class="form-group">
                <label>Add Tag:</label>
                <input class="form-control" aria-describedby="tagHelp" placeholder="enter a tag name..." v-model="tag">
                <small id="tagHelp" class="form-text text-muted">You can add a total of 10 tags.</small>
            </div>

            <button class="btn btn-primary" @click.prevent="addTag">Add</button>
        </form>
</template>

<script>
    export default {
        data(){
            return {
                tag: ""
            }
        },
        methods: {
            addTag(){
                if(this.tag != ""){
                    this.$emit("tagAdded", this.tag.toLowerCase());
                    this.tag = "";
                }
            }
        }
    }
</script>
