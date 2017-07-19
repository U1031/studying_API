<template>
    <div class='profile'>
        <img :src='profile_img'>
    </div>
</template>

<script>
export default {
    name: 'profile',
    props: ['profile_img']
}
</script>

<style>

</style>
