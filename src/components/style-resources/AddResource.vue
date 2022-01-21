<template>
    <base-dialog  v-if="inputIsInvalid" title="Invalid Input" @close="confirmError">
        <template #default>
            <p>Double check input values</p>
        </template>
        <template #actions>
            <base-button @click="confirmError"> Okay</base-button>
        </template>
    </base-dialog>
    <base-card>
        <form @submit.prevent="submitData">
            <h2> Add Resource</h2>
            <div class="form-control">
                <label> Title </label>
                <input id="title" name="title" type="text" ref="titleInput" />
            </div>

            <div class="form-control">
                <label> Description </label>
                <textarea id="description" name="description" ref="descInput" />
            </div>

            <div class="form-control">
                <label> Link </label>
                <input id="title" name="title" type="text" ref="urlInput"/>
            </div>

            <div class="form-control">
                <base-button type="submit">Add Resource</base-button>
            </div>
        </form>
    </base-card>
</template>

<script>

export default{
    inject: ['addResource'],
    data(){
        return{
            inputIsInvalid: false,
        }
    },
    methods:{
        submitData(){
            const enteredTitle = this.$refs.titleInput.value;
            const enteredDescription = this.$refs.descInput.value;
            const enteredUrl = this.$refs.urlInput.value;

            if(enteredTitle.trim === '' || enteredDescription.trim === ''|| enteredUrl.trim === ''){
                this.inputIsInvalid = true;
                return
            }
            this.addResource(enteredTitle, enteredDescription, enteredUrl);
        },
        confirmError(){
            this.inputIsInvalid = false;
        }
    }
}
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #8AF3FF;
  background-color: #ffefef;
}

.form-control {
  margin: 1rem 0;
}
</style>
