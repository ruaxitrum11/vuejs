<template>
    <div class="list-user">
        <table class="tbl-list-user">
            <thead>
            <th>Name</th>
            <th>Location</th>
            <th>DOB</th>
            </thead>
            <tbody>
            <tr v-for="user in totalUser">
                <td><a @click="selectUser(user)">{{ user.name.title }} - {{ user.name.last }} {{ user.name.first }}</a></td>
                <td>{{ user.location.city }}</td>
                <td>{{ user.dob }}</td>
            </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    import data from './data.json'
    export default {
        data() {
            return {
                users: data,
                object_data: {
                    gender: "male",
                    name:
                        {
                            title: "mr",
                            first: "Be Bong",
                            last: "Trung Hieu"
                        },
                    location:
                        {
                            street: "1861 jan pieterszoon coenstraat",
                            city: "maasdriel",
                            state: "zeeland",
                            postcode: 69217
                        },
                    email: "romain.hoogmoed@example.com",
                    dob: "1983-07-14 07:29:45"
                }
            }
        },
        methods: {
            selectUser(user) {
                this.$emit('parseUser', user)
            }
        },
        computed: {
            totalUser() {
                let user = this.users;
                let obj = this.object_data;
                user.push(obj);
                return user;
            }
        }
    }
</script>

<style lang="scss" scoped>
    .tbl-list-user {
        width: 100%;
    }
    a {
        cursor: pointer;
    }
</style>