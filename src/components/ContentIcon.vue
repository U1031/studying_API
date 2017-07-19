<template>
    <div class='content-icon'>
        <span v-for='key in keys'>
            <img :src='key.icon'>
        </span>
    </div>
</template>
<script>
export default {
    name: 'content-icon',
    data: function () {
        return {
            keys: [{
                name: 'name',
                icon: 'http://icooon-mono.com/i/icon_11324/icon_113241_64.png'
            }, {
                name: 'email',
                icon: 'http://icooon-mono.com/i/icon_12533/icon_125331_64.png'
            }, {
                name: 'birthday',
                icon: 'http://icooon-mono.com/i/icon_12662/icon_126621_64.png'
            }, {
                name: 'address',
                icon: 'http://icooon-mono.com/i/icon_11212/icon_112121_64.png'
            }, {
                name: 'phone_number',
                icon: 'http://icooon-mono.com/i/icon_16147/icon_161471_64.png'
            }, {
                name: 'password',
                icon: 'http://icooon-mono.com/i/icon_00014/icon_000141_64.png'
            },]
        }
    }
}
</script>

<style>
.content-icon img{
    width: 8%;
    height: 8%;
}
</style>

