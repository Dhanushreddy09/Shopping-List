<template>
    <div id="header">
        <nav class="navbar navbar-expand-lg bg-primary py-0 mb-3">
            <a class="navbar-brand text-white" href="/">Shopping List</a>
            <div id="search" class="ml-auto">
            <input type="text" class="form-control form-control-sm" placeholder="Search" v-model="search">
            </div>
            <div class="space"></div>
            <i class="fa fa-search text-white" aria-hidden="true"></i>
        </nav>
    </div>
</template>
<script>
export default {
    data:function(){
        return{
        search:''
        }
    }
}
</script>
<style scoped>
.space{
    width:5px;
}
</style>