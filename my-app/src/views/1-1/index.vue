<template>
    <div class="red">
        phoneInfo: {{phoneInfo}}<br/>
        zipCode: {{zipCode}}
        <PersonalInfo
            v-model="phoneInfo"
            :zip-code.sync="zipCode">
        </PersonalInfo>
        <!-- <PersonalInfo
            :phone-info="phoneInfo"
            @change="val => (phoneInfo = val)"
            :zip-code="zipCode"
            @update:zipCode="val => (zipCode = val)">
        </PersonalInfo> -->
    </div>
</template>

<script>
import PersonalInfo from './personInfo.vue';
export default {
    components: {
        PersonalInfo
    },
    data() {
        return {
            phoneInfo: {
                areaCode: '+86',
                phone: ''
            },
            zipCode: ''
        }
    }
}
</script>

<style>
.red {
    background-color: rgb(151, 201, 241);
    height: 200px;
}
</style>