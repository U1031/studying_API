<template>
    <div class='content-icon'>
        <div class='explain'>
           <span> {{explain[selectedKey]}}
            <br> {{mapping}}</span>
            
        </div>
        <div>
            <span v-for='key in keys' v-on:mouseover='handleMouseOver(key)'>
                <img :src='key.icon'>
            </span>
        </div>
    </div>
</template>
<script>
export default {
    name: 'content-icon',
    props: ['content_data'],
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
            },],
            explain: {
                name: 'Hi, My name is',
                email: 'My email address is',
                birthday: 'My birthday is',
                address: 'My address is',
                phone_number: 'My phone number is',
                password: 'My password is'
            },
            selectedKey: 'name',
            mapping: this.content_data.name.first + ' ' + this.content_data.name.last
        }
    },
    methods: {
        handleMouseOver: function (key) {
            this.selectedKey = key.name
            switch (this.selectedKey) {
                case 'name':
                    return this.mapping = this.content_data.name.first + ' ' + this.content_data.name.last

                case 'email':
                    return this.mapping = this.content_data.email

                case 'birthday':
                    return this.mapping = this.content_data.dob

                case 'address':
                    return this.mapping = this.content_data.location.postcode + ' ' + this.content_data.location.state + ' ' + this.content_data.location.city

                case 'phone_number':
                    return this.mapping = this.content_data.phone

                case 'password':
                    return this.mapping = this.content_data.login.password

            }
        }
    }
}
</script>

<style>
.content-icon img {
    width: 8%;
    height: 8%;
    position: relative;
    top: 80px;
}
.explain span{
    position: relative;
    top: 65px;
}
.content-icon{
    margin: 0px;
    width: 100%;
    height: 200px;
    position: relative;
    background-color: none;    
}
</style>

