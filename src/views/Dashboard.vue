<template>
    <div class="dashboard">
        <h1 class="subheading grey--text">Dashboard</h1>

        <v-container class="my-5">
            <v-card flat v-for="project in projects"> 
                <v-layout row wrap :class="`pa-3 project ${project.status}`">
                    <v-flex xs12 md6>
                        <div class="caption grey--text">{{ project.title }}</div>
                        <div>{{ project.content }}</div>
                    </v-flex>
                    <v-flex xs6 sm4 md2>
                        <div class="caption grey--text">Person</div>
                        <div>{{ project.person }}</div>
                    </v-flex>
                    <v-flex xs6 sm4 md2>
                        <div class="caption grey--text">Due by</div>
                        <div>{{ project.due }}</div>
                    </v-flex>
                    <v-flex xs2 sm4 md2>
                        <div class="caption grey--text">Status</div>
                        <div>{{ project.status }}</div>
                    </v-flex>
                </v-layout>
                <v-divider></v-divider>
            </v-card> 
        </v-container>

    </div>
</template>

<script>

export default {
    data() {
        return {
            projects: [
                { title: 'Design a new blablabla', person: 'The Moda Foca', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'Design a new blablabla', person: 'The Moda Foca', due: '1st Jan 2019', status: 'complete', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'Design a new blablabla', person: 'The Moda Foca', due: '1st Jan 2019', status: 'complete', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'Design a new blablabla', person: 'The Moda Foca', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'}
            ]
        }
    }
}
</script>

<style>
.project.complete{
    border-left: 4px solid #3cd1c2;
}

.project.ongoing{
    border-left: 4px solid orange;
}

.project.complete{
    border-left: 4px solid tomato;
}
</style>
