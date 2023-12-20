<script setup>
import { ref, computed } from 'vue'

const childCount = ref(1)
const flexDirection = ref('')
const flexWrap = ref('')
const flexJustifyContent = ref('')
const flexAlignItems = ref('')
const flexSelf = ref('')

const flexClass = computed(() => {
    let classes = [
        flexDirection.value,
        flexWrap.value,
        flexJustifyContent.value,
        flexAlignItems.value,
        flexSelf.value
    ]

    return classes.join(' ')
})
</script>
<template>
    <div class="container py-5" style="height: 100vh;">
        <div class="row">
            <div class="col-md-4">
                <div class="card mt-3" style="width: 18rem;">
                    <a href="javascript: void(0)" class="text-decoration-none">
                        <div class="card-body">
                            <h5 class="card-title">Flexbox</h5>
                            <p class="card-text">A CSS layout module.</p>
                        </div>
                    </a>
                </div>
            </div>
            <div class="col-md-8">
                <div class="form-group">
                    <label>Child Count:</label>
                    <input type="number" min="1" v-model="childCount" class="form-control">
                </div>
                <div class="form-group">
                    <label>Flex Direction:</label>
                    <select class="form-select" v-model="flexDirection">
                        <option value="">-- Please select --</option>
                        <option value="flex-sm-row-reverse">Sm-Row-Reverse</option>
                        <option value="flex-sm-column">Sm-Column</option>
                        <option value="flex-sm-column-reverse">Sm-Column-Reverse</option>
                        <option value="flex-md-row">Md-Row</option>
                        <option value="flex-md-row-reverse">Md-Row-Reverse</option>
                        <option value="flex-md-column">Md-Column</option>
                        <option value="flex-md-column-reverse">Md-Column-Reverse</option>
                        <option value="flex-lg-row">Lg-Row</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Flex Wrap:</label>
                    <select class="form-select" v-model="flexWrap">
                        <option value="">-- Please select --</option>
                        <option value="flex-sm-wrap-reverse">Sm-Wrap-Reverse</option>
                        <option value="flex-md-nowrap">Md-Nowrap</option>
                        <option value="flex-md-wrap">Md-Wrap</option>
                        <option value="flex-md-wrap-reverse">Wrap-Reverse</option>
                        <option value="flex-lg-nowrap">Lg-Nowrap</option>
                        <option value="flex-lg-wrap">Lg-Wrap</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Justify Content:</label>
                    <select class="form-select" v-model="flexJustifyContent">
                        <option value="">-- Please select --</option>
                        <option value="justify-content-sm-start">Sm-Start</option>
                        <option value="justify-content-sm-end">Sm-End</option>
                        <option value="justify-content-sm-center">Sm-Center</option>
                        <option value="justify-content-sm-between">Sm-Between</option>
                        <option value="justify-content-sm-around">Sm-Around</option>
                        <option value="justify-content-sm-evenly">Sm-Evenly</option>
                        <option value="justify-content-md-start">Md-Start</option>
                        <option value="justify-content-md-end">Md-End</option>
                        <option value="justify-content-md-center">Md-Center</option>
                        <option value="justify-content-md-between">Md-Between</option>
                        <option value="justify-content-md-around">Md-Around</option>
                        <option value="justify-content-md-evenly">Md-Evenly</option>
                        
                    </select>
                </div>
                <div class="form-group">
                    <label>Align Items:</label>
                    <select class="form-select" v-model="flexAlignItems">
                        <option value="">-- Please select --</option>
                        <option value="align-items-lg-start">Lg-Start</option>
                        <option value="align-items-lg-end">Lg-End</option>
                        <option value="align-items-lg-center">Lg-Center</option>
                        <option value="align-items-lg-baseline">Lg-Baseline</option>
                        <option value="align-items-lg-stretch">Lg-Stretch<option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Align Self:</label>
                    <select class="form-select" v-model="flexSelf">
                        <option value="">-- Please select --</option>
                        <option value="align-self-start">Start</option>
                        <option value="align-self-end">End</option>
                        <option value="align-self-center">Center</option>
                        <option value="align-self-baseline">Baseline</option>
                        <option value="align-self-stretch">Stretch</option>
                    </select>
                </div>
                <div class="mt-5">
                    <div style="width: 100%; height: 400px;"
                        class="bg-primary bg-opacity-10 d-flex border border-4 border-warning" :class="flexClass">
                        <div v-for="child in childCount" :key="child"
                            class="p-5 bg-primary text-center d-flex align-items-center justify-content-center fs-1 text-white border border-2 border-dark">
                            {{ child }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
