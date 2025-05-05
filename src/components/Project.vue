<script setup>
import { useRoute } from 'vue-router';
import SchoolProjects from '@/assets/data/school_projects.json'
import PersonalProjects from '@/assets/data/personal_projects.json'
import WorkProjects from '@/assets/data/work_projects.json'
import { computed } from 'vue';

const route = useRoute();
const projectID = route.params.id;
const projects = [SchoolProjects, PersonalProjects, WorkProjects].flat();

const project = computed(()=> projects.find(p => p.id === projectID));

</script>

<template>
<h1>{{ project.title }}</h1>
</template>