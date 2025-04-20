<template>
    <div>
        <p><strong>Full name</strong>: {{ fullname }}</p>
        <p><strong>Age</strong>: {{ age }} years</p>
    </div>
</template>

<script>
export default {
    // props: ['firstName', 'lastName', 'age'],
    props: {
        firstName: String,
        lastName: String,
        // age: Number
        age: [Number, String]
    },
    computed: {
        fullname() {
            return this.firstName + ' ' + this.lastName;
        }
    }
}
</script>