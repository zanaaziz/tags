<template>
    <div class="row">
        <app-tag v-for="(tag, index) in tags" :key="tag" @click.native="deleteTag(index)">{{ tag }}</app-tag>
    </div>
</template>

<script>
    import Tag from "./Tag.vue";

    export default {
        props: ['tags'],
        components: {
            appTag: Tag
        },
        methods: {
            deleteTag(index){
                if (confirm("Are you sure that you want to delete this tag?")) {
                    this.$emit("tagDeleted", index);
                }
            }
        }
    }
</script>
