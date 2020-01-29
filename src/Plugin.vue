<template>
  <div class="box-model">
    <div class="box-model__margin relative">
      <span class="box-model__title">margin</span>
      <div class="box-model__margin-top">
        <input
          type="text"
          placeholder="-"
          v-model="model.marginTop"
          class="input-number"
        />
      </div>
      <div class="box-model__margin-bottom">
        <input
          type="text"
          placeholder="-"
          v-model="model.marginBottom"
          class="input-number"
        />
      </div>
      <div class="box-model__margin-left">
        <input
          type="text"
          placeholder="-"
          v-model="model.marginLeft"
          class="input-number"
        />
      </div>
      <div class="box-model__margin-right">
        <input
          type="text"
          placeholder="-"
          v-model="model.marginRight"
          class="input-number"
        />
      </div>
      <div class="box-model__border relative">
        <span class="box-model__title">border</span>
        <div class="box-model__border-top">
          <input
            type="text"
            placeholder="-"
            v-model="model.borderTop"
            class="input-number"
          />
        </div>
        <div class="box-model__border-bottom">
          <input
            type="text"
            placeholder="-"
            v-model="model.borderBottom"
            class="input-number"
          />
        </div>
        <div class="box-model__border-left">
          <input
            type="text"
            placeholder="-"
            v-model="model.borderLeft"
            class="input-number"
          />
        </div>
        <div class="box-model__border-right">
          <input
            type="text"
            placeholder="-"
            v-model="model.borderRight"
            class="input-number"
          />
        </div>
        <div class="box-model__padding relative">
          <span class="box-model__title">padding</span>
          <div class="box-model__padding-top">
            <input
              type="text"
              placeholder="-"
              v-model="model.paddingTop"
              class="input-number"
            />
          </div>
          <div class="box-model__padding-bottom">
            <input
              type="text"
              placeholder="-"
              v-model="model.paddingBottom"
              class="input-number"
            />
          </div>
          <div class="box-model__padding-left">
            <input
              type="text"
              placeholder="-"
              v-model="model.paddingLeft"
              class="input-number"
            />
          </div>
          <div class="box-model__padding-right">
            <input
              type="text"
              placeholder="-"
              v-model="model.paddingRight"
              class="input-number"
            />
          </div>
          <div class="box-model__dimensions relative">
            <span class="box-model__title">dimensions</span>
            ? x ?
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mixins: [window.Storyblok.plugin],
  methods: {
    initWith() {
      return {
        // needs to be equal to your storyblok plugin name
        plugin: "spacing-plugin",
        paddingTop: "-",
        paddingBottom: "-",
        paddingLeft: "-",
        paddingRight: "-",
        marginTop: "-",
        marginBottom: "-",
        marginLeft: "-",
        marginRight: "-",
        borderTop: "-",
        borderBottom: "-",
        borderLeft: "-",
        borderRight: "-"
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
.input-number {
  text-align: center;
  width: 24px !important;
  height: 20px !important;
  font-size: 10px !important;
  padding: 0 !important;
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
