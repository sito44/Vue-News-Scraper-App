<template v-if="
linkTitle1 &&
linkDate1 &&
linkUrl1 &&
linkTitle2 &&
linkDate2 &&
linkUrl2 &&
linkTitle3 &&
linkDate3 &&
linkUrl3 &&
linkTitle4 &&
linkDate4 &&
linkUrl4 &&
linkTitle5 &&
linkDate5 &&
linkUrl5 &&
linkTitle6 &&
linkDate6 &&
linkUrl6 
">
    <div class="container">
        
        <div class="link-container">
            <a v-if="linkDate1 && linkUrl1" :href="linkUrl1" target="_blank"><h3>{{ linkTitle1 }}</h3></a>
            <span v-if="linkDate1">{{ linkDate1 }}</span>
        </div>
        <div class="link-container">
            <a v-if="linkDate2 && linkUrl2" :href="linkUrl2" target="_blank"><h3>{{ linkTitle2 }}</h3></a>
            <span v-if="linkDate2">{{ linkDate2 }}</span>
        </div>
        <div class="link-container">
            <a v-if="linkDate3 && linkUrl3" :href="linkUrl3" target="_blank"><h3>{{ linkTitle3 }}</h3></a>
            <span v-if="linkDate3">{{ linkDate3 }}</span>
        </div>
        <div class="link-container">
            <a v-if="linkDate4 && linkUrl4" :href="linkUrl4" target="_blank"><h3>{{ linkTitle4 }}</h3></a>
            <span v-if="linkDate4">{{ linkDate4 }}</span>
        </div>
        <div class="link-container">
            <a v-if="linkDate5 && linkUrl5" :href="linkUrl5" target="_blank"><h3>{{ linkTitle5 }}</h3></a>
            <span v-if="linkDate5">{{ linkDate5 }}</span>
        </div>
        <div class="link-container">
            <a v-if="linkDate6 && linkUrl6" :href="linkUrl6" target="_blank"><h3>{{ linkTitle6 }}</h3></a>
            <span v-if="linkDate6">{{ linkDate6 }}</span>
        </div>

    </div>
</template>

<script>
    export default {
        props: [
            'linkDate1',
            'linkTitle1',
            'linkUrl1',
            'linkDate2',
            'linkTitle2',
            'linkUrl2',
            'linkDate3',
            'linkTitle3',
            'linkUrl3',
            'linkDate4',
            'linkTitle4',
            'linkUrl4',
            'linkDate5',
            'linkTitle5',
            'linkUrl5',
            'linkDate6',
            'linkTitle6',
            'linkUrl6',
        ]
    }
</script>

<style lang="scss" scoped>
.container {
    background-color: white;
    width: 100vw;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    padding: .04rem;
    .link-container {
        width: 30vw;
        flex: 0 4 auto;
        text-align: left;
        a {
            color: rgba(98, 113, 111, 1)
        }
        

    }
}
</style>