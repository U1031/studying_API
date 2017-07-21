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
.profile {

    height: 120px;
    background: lightslategray;
    border-top-left-radius: 2%;
    border-top-right-radius: 2%;
}

.profile img{
    position: relative;
    display: inline-block;
    background: #fff;
    padding: 5px;
    width: 150px;
    height: 150px;
    top: 10px;
    border-radius: 50%;
    margin-bottom: 30px;
    border: 1px solid rgba(0, 0, 0, .25);
}
</style>
