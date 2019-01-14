<template>
  <div class="projects">
    <h1 class="subheading grey--text">Projects</h1>
    <v-container class="my-5">
        <v-expansion-panel>
            <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
                <div slot="header">{{ project.title }}</div>
                <v-card>
                    <v-card-text class="px-4 grey--text">
                        <div class="font-weight-bold">due by {{ project.due }}</div>
                        <div>{{ project.content }}</div>
                    </v-card-text>
                </v-card>
            </v-expansion-panel-content>
        </v-expansion-panel>
    </v-container>
  </div>
</template>

<script>
export default {
    data(){
        return {
            projects: [
                { title: 'Design a new blablabla', person: 'Punisher', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'Nigga this is a taitou', person: 'Wolverine', due: '1st Jan 2019', status: 'complete', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'Another description', person: 'Ryu', due: '1st Jan 2019', status: 'complete', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
                { title: 'This one here is the best', person: 'Punisher', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'},
 { title: 'I forgot this one, but not anymore', person: 'Yori', due: '1st Jan 2019', status: 'overdue', content: 'Lorem Ipsum dollor sis amet consctetus moda floca.'}
            ]
        }
    },
    computed: {
        myProjects(){
            return this.projects.filter(project =>{
                return project.person === 'Punisher'
            })
        }
    }
}
</script>
