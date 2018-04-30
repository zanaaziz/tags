<template>
    <div class="col-sm-2">
        <div class="card tag text-center">
            <slot></slot>
        </div>
    </div>
</template>

<script>
</script>

<style>
    .tag{
        cursor: pointer;
        margin-bottom: 1em;
        padding: 1em;
        color: #4d4d4d;
    }

    .tag:hover{
        background-color: #ffe2e2;
    }
</style>
