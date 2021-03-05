<template>
  <div id="App">
    <div id="obiDiv">
      <div id="obiCanvasDiv">
        <component :is="component.type" v-for="(component, i) in components" :propsData="component.propsData" :key="i"
        :ref="component.propsData.ID"></component>
        <br />
        <br />
        <br />
        <!-- <Info :propsData="components[0].propsData" ref="info"></Info>
         <Button :propsData="components[2].propsData" @click="$refs.info.SetText('test')"></Button>
          -->
          <!--$refs.ExampleInfo.SetText('Yeni Text')   @click="$refs.ExampleInfo.SetText('Yeni Text')" -->
      </div>
    </div>
  </div>
</template>

<script>
import Info from "./components/Info.vue";
import Button from "./components/Button.vue";
import DataDisplayer from "./components/DataDisplayer.vue";

export default {
  components: {
    Info,
    Button,
    DataDisplayer
  },
  data() {
    return {
      components: [
        {
          type: "Info",
          propsData: {
            ID: "ExampleInfo",
            Text:
              "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ",
            Icon: "blue_i",
            Visible: "true",
            HeaderText: "",
          }
        },
        {
          type: "DataDisplayer",
          propsData: {
            ID: "ExampleDataDisplayer",
            LabelAndValue: [{Label:"Ad Soyad",Value:"Bahar Atlı"},{Label:"E-Posta",Value:"baharatli@gmail.com"}, {Label:"Telefon",Value:"5345554433"},{Label:"Adres",Value:"İstanbul"}],
            Visible: "true",
            Header: "Kişisel Bilgiler"
          },
        },
        // {
        //   type: "Info",
        //   ref:"info",
        //   propsData: {
        //     ID: "ExampleInfo",
        //     Text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
        //     Icon: "blue_i",
        //     Visible: "true",
        //     HeaderText: ""
        //   },
        // },
        //  {
        //   type: "Button",
        //   propsData: {
        //     ID: "ExampleButton",
        //     Text: "TIKLA",           
        //   },
        //   onClick:"ExampleInfo.SetText('Yeni Text')"
        // },
      ]
    };
  },
};
</script>

<style>
#app {
  height: 100%;
  min-height: 100%;
  position: relative;
  width: 100%;
}

#App {
  width: 100%;
  height: 100%;
  color: black;
  background-color: #f2f2f2;
}

#obiCanvasDiv {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  padding: 20px 20px 20px 20px;
  max-width: 788px;
}

#obiDiv {
  background-color: white;
  color: black;
  margin-right: 50px;
  max-width: 788px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

#obiDiv * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  margin: 0;
}
</style>