<template>
    <div>
        <p><strong>Full name</strong>: {{ fullname }}</p>
        <p><strong>Age</strong>: {{ age }} years</p>
    </div>
</template>

<script>
export default {
    props: ['firstName', 'lastName', 'age'],
    computed: {
        fullname() {
            return this.firstName + ' ' + this.lastName;
        }
    }
}
</script>