<template>
    <div>
        <TreeItem v-for="item in treeData" :key="item.id" :item="item" />
    </div>
</template>

<script>
import TreeItem from './components/TreeItem.vue';
import { fetchData } from './fetchData.ts';
export default {
    name: 'App',
    components: { TreeItem },
    data() {
        return {
            treeData: [],
        };
    },
    async created() {
        this.treeData = await fetchData();
    },
};
</script>
