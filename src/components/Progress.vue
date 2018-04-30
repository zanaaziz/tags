<template>
    <div class="progress" style="height: 2.5em; margin-bottom: 1em; background-color: #eeeeee;">
        <div class="progress-bar" role="progressbar" :style="{width: (numOfTags / maxNumOfTags) * 100 + '%'}" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100"><span v-if="numOfTags >= 1">{{ numOfTags }}</span></div>
    </div>
</template>

<script>
    export default {
        props: ["maxNumOfTags", "numOfTags"]
    }
</script>
