<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButton"> Guides</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButton"> Add </base-button>
    </base-card>
    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource';

export default{
    components:{
        StoredResources,
        AddResource,
    },
    data(){
        return{
            selectedTab: 'stored-resources',
            storedResources: [
                {
                    id: 'pinterest',
                    title: 'Pinterest',
                    description: 'A great app to find inspiration for styles',
                    link: 'https://pinterest.com/'
                },
                {
                    id: 'uniqlo',
                    title: 'Uniqlo',
                    description: 'Comfort, Japanese Street Style',
                    link: 'https://www.uniqlo.com/us/en/home/'
                },
            ]
        };
    },
    provide(){
        return{
            resources: this.storedResources,
            addResource: this.addResource,
            deleteResource: this.deleteResource,
        }
    },
    computed:{
        storedResButton(){
            return this.selectedTab === 'stored-resources' ? null : 'flat';
        },
        addResButton(){
            return this.selectedTab === 'add-resources' ? null : 'flat';
        }
    },
    methods: {
        setSelectedTab(tab){
            this.selectedTab = tab;
        },
        addResource(title,description,url){
            const newResource = {
                id: new Date().toISOString,
                title: title,
                description: description,
                link: url,
            };
            this.storedResources.unshift(newResource);
            this.selectedTab = 'stored-resources';
        },
        deleteResource(resId){
            const resIndex = this.storedResources.findIndex(res => res.id === resId);
            this.storedResources.splice(resIndex,1);
        }
    }
}

</script>
