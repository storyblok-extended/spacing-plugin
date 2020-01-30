<template>
  <div class="container">
    <div class="button-group">
      <button class="active">All (s)</button>
      <button>Medium UP</button>
      <button>Large UP</button>
    </div>
    <div class="box-model">
      <div class="box-model__margin relative">
        <span class="box-model__title">margin</span>
        <div class="box-model__margin-top">
          <select class="select-breakpoint" v-model="model.marginTop">
            <option :key="option" v-for="option in options" :value="option">{{
              option
            }}</option>
          </select>
        </div>
        <div class="box-model__margin-bottom">
          <select class="select-breakpoint" v-model="model.marginBottom">
            <option :key="option" v-for="option in options" :value="option">{{
              option
            }}</option>
          </select>
        </div>
        <div class="box-model__margin-left">
          <select class="select-breakpoint" v-model="model.marginLeft">
            <option :key="option" v-for="option in options" :value="option">{{
              option
            }}</option>
          </select>
        </div>
        <div class="box-model__margin-right">
          <select class="select-breakpoint" v-model="model.marginRight">
            <option :key="option" v-for="option in options" :value="option">{{
              option
            }}</option>
          </select>
        </div>
        <div class="box-model__padding relative">
          <span class="box-model__title">padding</span>
          <div class="box-model__padding-top">
            <select class="select-breakpoint" v-model="model.paddingTop">
              <option :key="option" v-for="option in options" :value="option">{{
                option
              }}</option>
            </select>
          </div>
          <div class="box-model__padding-bottom">
            <select class="select-breakpoint" v-model="model.paddingBottom">
              <option :key="option" v-for="option in options" :value="option">{{
                option
              }}</option>
            </select>
          </div>
          <div class="box-model__padding-left">
            <select class="select-breakpoint" v-model="model.paddingLeft">
              <option :key="option" v-for="option in options" :value="option">{{
                option
              }}</option>
            </select>
          </div>
          <div class="box-model__padding-right">
            <select class="select-breakpoint" v-model="model.paddingRight">
              <option :key="option" v-for="option in options" :value="option">{{
                option
              }}</option>
            </select>
          </div>
          <div class="box-model__dimensions relative">
            content
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mixins: [window.Storyblok.plugin],
  data: function() {
    return {
      options: ["-", "xs", "s", "m", "l", "xl", "xxl"]
    };
  },
  methods: {
    initWith() {
      return {
        // needs to be equal to your storyblok plugin name
        plugin: "spacing-plugin",
        paddingTop: "",
        paddingBottom: "",
        paddingLeft: "",
        paddingRight: "",
        marginTop: "",
        marginBottom: "",
        marginLeft: "",
        marginRight: ""
      };
    },
    pluginCreated() {
      // eslint-disable-next-line
      console.log(
        "View source and customize: https://github.com/storyblok/storyblok-fieldtype"
      );
    }
  },
  watch: {
    model: {
      handler: function(value) {
        this.$emit("changed-model", value);
      },
      deep: true
    }
  }
};
</script>

<style>
.active {
  background-color: #efefef;
}

.container {
  display: flex;
  flex-direction: column;
}

.button-group {
  margin: 8px 0;
  display: flex;
  align-self: flex-end;
}

.input-number {
  text-align: center;
  width: 24px !important;
  height: 20px !important;
  font-size: 10px !important;
  padding: 0 !important;
}

.select-breakpoint {
  text-align: center;
  width: 24px !important;
  height: 20px !important;
  font-size: 10px !important;
  padding: 0 !important;
  background-image: none !important;
}

.box-model {
  background-color: #efefef;
  text-align: center;
  font-size: 12px;
}

.box-model .relative {
  position: relative;
  padding: 24px 32px;
}

.box-model__margin {
  background-color: #efefef;
}

.box-model__border {
  background-color: #dfdfdf;
}

.box-model__padding {
  background-color: #cfcfcf;
}

.box-model .box-model__dimensions {
  background-color: #efefef;
  padding: 8px 0px;
}

.box-model__title {
  position: absolute;
  line-height: 8px;
  font-size: 8px;
  top: 2px;
  left: 2px;
}

/* margin */
.box-model__margin-top {
  position: absolute;
  z-index: 1;
  top: 2px;
  left: 50%;
  transform: translateX(-50%);
}

.box-model__margin-bottom {
  position: absolute;
  z-index: 1;
  bottom: 2px;
  left: 50%;
  transform: translateX(-50%);
}

.box-model__margin-left {
  position: absolute;
  z-index: 1;
  top: 50%;
  left: 2px;
  transform: translateY(-50%);
}

.box-model__margin-right {
  position: absolute;
  z-index: 1;
  top: 50%;
  right: 2px;
  transform: translateY(-50%);
}

/* border */
.box-model__border-top {
  position: absolute;
  z-index: 1;
  top: 2px;
  left: 50%;
  transform: translateX(-50%);
}

.box-model__border-bottom {
  position: absolute;
  z-index: 1;
  bottom: 2px;
  left: 50%;
  transform: translateX(-50%);
}

.box-model__border-left {
  position: absolute;
  z-index: 1;
  top: 50%;
  left: 2px;
  transform: translateY(-50%);
}

.box-model__border-right {
  position: absolute;
  z-index: 1;
  top: 50%;
  right: 2px;
  transform: translateY(-50%);
}

/* padding */
.box-model__padding-top {
  position: absolute;
  z-index: 1;
  top: 2px;
  left: 50%;
  transform: translateX(-50%);
}

.box-model__padding-bottom {
  position: absolute;
  z-index: 1;
  bottom: 2px;
  left: 50%;
  transform: translateX(-50%);
}

.box-model__padding-left {
  position: absolute;
  z-index: 1;
  top: 50%;
  left: 2px;
  transform: translateY(-50%);
}

.box-model__padding-right {
  position: absolute;
  z-index: 1;
  top: 50%;
  right: 2px;
  transform: translateY(-50%);
}
</style>
