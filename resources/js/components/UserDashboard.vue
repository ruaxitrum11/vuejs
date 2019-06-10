<template>
    <div class="user-dashboard">
        <div class="user-dashboard">
            <div class="list-user-comp">
                <h4>List User</h4>
                <list-user @parseUser="childrenParseUser"></list-user>
            </div>
            <hr>
            <div class="user-detail-comp">
                <h4>User Detail</h4>
                <user-detail :userDetailParse = "userDetailParse"></user-detail>
            </div>
        </div>
    </div>
</template>

<script>
    import ListUser from './ListUser.vue'
    import UserDetail from './UserDetail.vue'
    export default {
        components: {
            ListUser,
            UserDetail
        },
        data() {
            return {
                userDetailParse: {}
            }
        },
        methods: {
            childrenParseUser(user) {
                this.userDetailParse = user
            }
        }
    }
</script>

<style lang="scss" scoped>
</style>