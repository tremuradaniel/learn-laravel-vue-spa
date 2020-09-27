<template>
    <div>
        <h1>My Achievements</h1>
        <ul>
            <li v-for="(achievement, index) in achievements" :key="index">{{achievement}}</li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            achievements: []
        }
    },
    created () {
        axios
            .get('/api/achievements?api_token=akfpHKzjC0Cnv3ciMggaEvFLnR8DAPDyeSvNA0nmbjwNe')
            .then(response => {
                this.achievements = response.data;
            })
    }
}
</script>