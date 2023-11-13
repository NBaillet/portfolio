<template>
    <div class="bg-stone-800 m-2 rounded-md text-center border-2 border-stone-600">
        <img class="inline-block p-2" alt="Vue logo" src="../assets/logo.png" />
        <h2 class="font-bold text-3xl">Nathan Baillet</h2>
        <ul class="text-stone-400 text-left mt-4">
            <li v-for="skill in skills" :key="skill[0]" @click="toggleDetail()">
                {{ skill[0] }}
                <label v-if="showDetail" class="text-stone-500">- {{ skill[1] }}</label>
            </li>
        </ul> 
    </div>
</template>

<script setup>

import { ref } from 'vue' 

const skills = 
[
    ['C#/.NET Framework',       '3 years professional experience'],
    ['Microsoft SQL Server',    '3 years professional experience'],
    ['VB.NET',                  '1+ years professional legacy support experience'],
    ['Javascript + HTML & CSS', 'working knowledge'],
    ['SVN + Git',               'variety of experience'],
    ['SAS',                     'SAS base programmer certification along with industry experience'],
    ['Java',                    'university with group project experience'],
    ['Windows, Linux + Mac',    'variety of experience'],
];

let showDetail = ref(false);

function toggleDetail()
{
    showDetail.value = !showDetail.value;
}

</script>