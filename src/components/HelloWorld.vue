<template>
    <div>Test</div>
    <div>
      <textarea v-model="inputData" @keypress="handleText(inputData)"></textarea>
      <button @click="handleText('Test')">Say hello</button>
      <div>
        <h3>Converted List:</h3>
  
        <h1>test</h1>
  
        <v-chip closable v-for="(item, index) in itemList" :key="index">{{
          item
        }}</v-chip>
        <h1>test 2</h1>
        <div>{{ inputData }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        inputData: "",
        itemList: [],
        name: "HelloWorld",
      };
    },
    methods: {
      handlePaste(event) {
        const clipboardData = event.clipboardData || window.clipboardData;
        const pastedData = clipboardData.getData("text");
  
        // Split pasted data by newline to create the list of items
        const items = pastedData.split(",").filter((item) => item.trim() !== "");
        this.itemList = items;
      },
      handleText(event) {
        //const clipboardData = event.clipboardData || window.clipboardData;
        //const pastedData = clipboardData.getData("text");
        console.log(event);
        // Split pasted data by newline to create the list of items
         const items = event.split(",").filter((item) => item.trim() !== "");
         console.log(items);
        //debug.log(items);
        // this.itemList = items;
      },
      showAlert: (message) => {
        alert(message);
      },
    },
  };
  </script>
  
  <style>
  /* Add your component's styles here */
  </style>
  