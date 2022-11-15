<template>
    <div class="search-bar ps-2 my-3">
        <select name="category" id="">
            <option selected value="select category">Select category</option>
            <option value="alive">Alive</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'NavbarComponent'
}
</script>

<style lang="scss" scoped>
.search-bar select {
    padding: 5px;
    font-size: 13px;
    border-radius: 5px;
}
</style>