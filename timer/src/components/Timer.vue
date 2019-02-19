<template>
    <div>
        <large-timer :time=this.time></large-timer>
    </div>
</template>

<script>

import LargeTimer from './LargeTimer.vue'

export default {
    name: 'Timer',
    props: {},
    components: {
        'large-timer': LargeTimer
    },
    data: function() {
        return {
            time: 0,
            task: 0,
            name: '',
            tasks: [],
            taskRecords: []
        }
    },
    mounted: function() {
        const timerData = [
            {
                name: 'example task 1',
                subtasks: ['example subtask 1', 'example subtask 2', 'example subtask 3']
            }
        ]
        this.name = timerData[0].name
        timerData[0].subtasks.forEach((e,i) => {
            console.log(e)
            this.tasks.push(e)
        })
        this.count(true)
    },
    methods: {
        count: function(mainTimer = false) {
            if(mainTimer) {
                this.time++
                setTimeout(this.count.bind(null, true), 1000)
            }
            else this[`subtask_${task}`] ++
        },
        selectTask: function (t) {

        } 
    }
}
</script>