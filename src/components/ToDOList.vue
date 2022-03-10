<template>
<div class="container">
    <div class="row">
        <div class="max-w-md mx-auto  rounded-lg p-6 m-6 shadow-xl ring-4">
            <h1 class="text-red-500 text-lg uppercase font-bold">TO DO LIST VUE JS</h1>
            <div class="rounded" v-for="tasks in task" :key="tasks.id">
               <li class="block text-justify hover:text-black hover:border-pink-500 bg-gray-100 rounded  cursor-pointer mt-4 p-4 ring-2">{{ tasks.id }}: {{ tasks.content }}</li>
            </div>
            <button @click.prevent="showForm" class="bg-blue-800 py-2 px-4 mt-5 rounded text-white font-sans font-extrabold focus:ring-2 focus:bg-blue-500" v-if="NewToDoList">Add New</button>
            <div class="max-w-lg mx-auto" v-if="showFormAddition">
                <form action="" class="full relative block" id="addForm">
                    <div class="pt-4 pb-2 relative m-auto">
                        <input type="text" class="full focus:border-blue-700 pt-4 pb-4 py-2 px-3 border-2" v-model="items">
                    <div id="error" class=" text-red-700 mt-3 p-3 rounded justify-between" style="display:none">
                            <span role="alert"></span>
                    </div>
                    </div>
                    <button @click.prevent='newTaskAddition' class="px-4 py-2 rounded bg-blue-700 text-white focus:ring-2 focus:bg-pink-600">Save Now..</button>
                    <div class="rounded text-justify block bg-gray-300 p-4 mt-2 text-pink-700 font-serif font-bold" v-if="items != ''">{{ items }}</div>
                </form>
            </div>
       </div>
    </div>
</div>
</template>

<script>
    // Logic
    export default {
        name: 'ToDOList',
        data() {
            return {
                items: '',
                id: '',
                error: '',
                NewToDoList: true,
                showSubmitButton: true,
                showFormAddition: false,
                showErrorMsg: false,
                task: [
                    {id: 1, content: 'I went To Farm Early In the Morning...!'},
                    {id: 2, content: 'I went To School Early In the Morning...!'},
                ],
            }
        },
        methods: {
                showForm () {
                    this.NewToDoList = false; //Hide Button Add New
                    this.showFormAddition = true; // Show Form For Addition
                },
                inputError() {
                    return this.error = "New Task is Required..";
                },
                newTaskAddition() {
                if(`${this.items}` == '')
                {
                    document.getElementById('error').style.display = 'block';
                    document.getElementById('error').innerHTML = this.inputError();
                }
                else{
                    // alert(`${this.items}`);
                    this.task.push({
                        id: this.id.length + 1,
                        content: this.items
                    });
                }
                this.items = '';
                this.showInput = false;
            }
        }
    }
</script>

<style>
/* Style */
</style>