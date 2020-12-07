<template>
    <div class="filters">
        <span 
            v-for="filter in filters" 
            :key="filter.value" 
            class="filter"
            :class="{ active: selected == filter.value}"
            @click="$emit('change-filter', filter.value)"
            >{{ filter.label }}</span>
    </div>
</template>

<script>
export default {
    name: 'TodoFilter',
    props: ['selected'],
    setup() {
        const filters = [
            {label: 'All', value: 'all'},
            {label: 'Done', value: 'done'},
            {label: 'Undone', value: 'todo'},
        ];
        return {
            filters
        }
    },
}
</script>

<style>

.filters {
    display: flex;
    margin: 24px 2px;
    color: #c0c2ce;
    font-size: 14px;
}
.filters .filter{
    margin-right: 14px;
    transition: .8s;
    cursor: pointer;
}
.filters .filter.active{
    color: #6b729c;
    transform: scale(1.2);
}
</style>