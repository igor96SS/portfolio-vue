<script setup>
import { useRoute } from 'vue-router';
import Project from '@/components/Project.vue';
import SchoolProjects from '@/assets/data/school_projects.json'
import PersonalProjects from '@/assets/data/personal_projects.json'
import WorkProjects from '@/assets/data/work_projects.json'
import { computed } from 'vue';
import BackButton from '@/components/BackButton.vue';


const route = useRoute();
const projectID = route.params.id;
const projects = [SchoolProjects, PersonalProjects, WorkProjects].flat();

const project = computed(()=> projects.find(p => p.id === projectID));

</script>

<template>
    <BackButton/>
    <Project :project="project"/>
</template>