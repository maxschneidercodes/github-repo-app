
<template>
    <div>
        <h1>GitHub Repos</h1>
        <div v-if="pending">
            <Spinner />
        </div>
        <div v-if="error">
            <p>Ein Fehler ist aufgetreten ({{ error }})</p>
        </div>
        <div v-else>
            <div class="row">
                <div class="col-md-auto" v-for="repo in reposData">
                    <Repo :repo="repo" />
                </div>
            </div>
            <div>
                <button class="btn btn-secondary mx-4" @click="next">next Page</button>
                <button class="btn btn-secondary m-4" @click="previous">previous Page</button>
            </div>
        </div>
    </div>
</template>

<script setup>
const page = ref(1)

const { data: reposData
    , pending
    , refresh
    , error } = await useFetch(() => `https://api.github.com/users/maxschneidercodes/repos?per_page=4&page=${page.value}`)

function previous() {
    if (page.value === 0) { return }
    page.value--
    refresh()
}
function next() {
    page.value++
    refresh()
}

</script>