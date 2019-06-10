<template>
    <div class="user-detail">
        <div class="user-detail-container" v-if="Object.keys(userDetailParse).length !== 0">
            <div class="user-name">
                {{ userName }}
            </div>
            <div class="user-email">
                {{ userEmail }}
            </div>
            <div class="user-dob">
                {{ userDOB }}
            </div>
            <div class="user-gender">
                {{ userGender }}
            </div>
            <div class="user-address">
                {{ userAddress }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            userDetailParse: {
                type: Object
            }
        },
        computed: {
            userName() {
                return  'Name: ' + this.userDetailParse.name.last + ' ' + this.userDetailParse.name.first
            },
            userEmail() {
                return  'Email: ' + this.userDetailParse.email
            },
            userDOB() {
                return  'DOB: ' + this.userDetailParse.dob
            },
            userGender() {
                return  'Gender: ' + this.userDetailParse.gender
            },
            userAddress() {
                return  'Address: ' + this.userDetailParse.location.city
            }
        }
    }
</script>

<style lang="scss" scoped>
</style>