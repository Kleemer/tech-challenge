<template>
    <div>
        <div
            @click="toggle"
            :style="{ cursor: hasChildren ? 'pointer' : 'default' }"
        >
            <span v-if="hasChildren">{{ isOpen ? '▼' : '▶' }}</span>
            <span v-else>•</span>
            {{ item.name }}
        </div>
        <div v-if="isOpen" style="padding-left: 1rem">
            <TreeItem
                v-for="child in item.children"
                :key="child.id"
                :item="child"
            />
        </div>
    </div>
</template>

<script>
export default {
    name: 'TreeItem',
    props: {
        item: Object,
    },
    data() {
        return {
            isOpen: true,
        };
    },
    computed: {
        hasChildren() {
            return this.item.children && this.item.children.length > 0;
        },
    },
    methods: {
        toggle() {
            if (this.hasChildren) {
                this.isOpen = !this.isOpen;
            }
        },
    },
};
</script>
