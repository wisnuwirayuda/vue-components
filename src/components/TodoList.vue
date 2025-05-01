<template>
    <ul class="list-group">
        <li class="list-group-item" v-for="item in items" :key="item.id">
            <slot v-bind="item"></slot>

            <!-- <p class="mb-0 pb-2">{{ item.name }}</p>
            <button class="btn btn-sm btn-success">Done</button> -->
        </li>
        <li class="list-group-item">
            <slot name="footer" :all="all" :todo="todo" :done="done">
                All: {{ all }} | Todo: {{ todo }} | Done: {{ done }}
            </slot>
        </li>
        <!-- <li class="list-group-item">All: {{ all }} | Todo: {{ todo }} | Done: {{ done }}</li> -->
    </ul>
</template>

<script>
export default {
    props: ['endpoint'],
    data: () => ({
        items: [],
        all: 3,
        todo: 1,
        done: 1
    }),
    methods: {
        mockApi() {
            this.items = [
                {
                    id: 1,
                    name: "Video Recording",
                    done: true
                },
                {
                    id: 2,
                    name: "Editing Recording",
                    done: true
                },
                {
                    id: 3,
                    name: "Publishing Recording",
                    done: true
                },
            ]
        }
    },
    mounted() {
        setTimeout(() => this.mockApi(), 1000);
    }
}
</script>