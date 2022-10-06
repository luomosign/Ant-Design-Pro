<template>
  <div class="mainDiv">
    <div>
      <select
        @change="handelAreaCodeChange">
        <option value="+86" label="+86"></option>
        <option value="+70" label="+70"></option>
        <option value="+92" label="+92"></option>
      </select>
      <input
        :value="phoneInfo.phone"
        type="text"
        placeholder="手机号"
        @input="handlePhoneChange"/>
    </div>
    <div>
      <input 
        :value="zipCode"
        type="text"
        placeholder="邮编"
        @input="handleZipCodeChange"/>
    </div>
  </div>
</template>

<script>

export default {
  name: 'PersonalInfo',
  model: {
    prop: "phoneInfo",
    event: "change"
  },
  props: {
    phoneInfo: Object,
    zipCode: String
  },
  methods: {
    handelAreaCodeChange(e) {
      console.log(e, 'handelAreaCodeChange')
      this.$emit("change", {
        ...this.phoneInfo,
        areaCode: e.target.value
      })
    },
    handlePhoneChange(e) {
      this.$emit("change", {
        ...this.phoneInfo,
        phone: e.target.value
      })
      
    },
    handleZipCodeChange(e) {
      this.$emit('update:zipCode', e.target.value)
    }
  }
}
</script>
<style>
.mainDiv {
  margin-top: 20px;
  text-align: left;
}
.mainDiv div {
  height: 60px;
  padding-left: 200px;
}
</style>