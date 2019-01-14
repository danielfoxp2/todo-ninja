<template>
    <div class="dashboard">
        <h1 class="subheading grey--text">Dashboard</h1>

        <v-container class="my-5">

            <v-layout row class="mb-3">
                <v-tooltip top>
                    <v-btn small flat color="grey" @click="sortBy('title')" slot="activator">
                        <v-icon left small>folder</v-icon>
                        <span class="caption text-lowercase">By project name</span>
                    </v-btn>
                    <span>Sort projects by project name </span>
                </v-tooltip>
                <v-tooltip top>
                    <v-btn small flat color="grey" @click="sortBy('person')" slot="activator">
                        <v-icon left small>person</v-icon>
                        <span class="caption text-lowercase">By person</span>
                    </v-btn>
                    <span>Sort projects by person</span>
                </v-tooltip>
            </v-layout>

            <v-card flat v-for="project in projects" :key="project.title"> 
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
                        <div class="right">
                            <v-chip small :class="`${project.status} white--text caption my-2`">{{ project.status }}</v-chip>
                        </div>
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
                { title: 'Design a new blablabla', person: 'Punisher', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'Nigga this is a taitou', person: 'Wolverine', due: '1st Jan 2019', status: 'complete', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'Another description', person: 'Ryu', due: '1st Jan 2019', status: 'complete', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'This one here is the best', person: 'Gouken', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
 { title: 'I forgot this one, but not anymore', person: 'Yori', due: '1st Jan 2019', status: 'overdue', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'}
 
            ]
        }
    },
    methods: {
        sortBy(prop){
            this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
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

.project.overdue{
    border-left: 4px solid tomato;
}

.v-chip.complete{
    background: #3cd1c2;
}

.v-chip.ongoing{
    background: orange;
}

.v-chip.overdue{
    background: tomato;
}
</style>
