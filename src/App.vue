<template>
    <p>
        Please build the structure you see in <code>PageTree.png</code> in the
        file explorer.
    </p>
    <p>
        The data for this structure should be loaded from
        <code>fetchData.js</code>.
    </p>
    <p>Useful icon characters are ▼ ▶ •</p>
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
