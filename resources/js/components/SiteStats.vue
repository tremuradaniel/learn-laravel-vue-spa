<template>
    <div>
        <h1 class="font-normal text-3xl text-grey-darkest leading-none mb-8">
            Stats
        </h1>
        <ul>
            <li>Total Series: {{ series }}</li>
            <li>Total Lessons: {{ lessons }}</li>
        </ul>
    </div>
</template>
<script>
export default {
    data () {
        return {
            series: 0,
            lessons: 0
        }
    },
    created () {
        axios.get('/api/stats')
        // deconstructing response in data
            .then(({ data }) => {
                this.series = data.series;
                this.lessons = data.lessons;
            });
    }
}
</script>