<template>
    <div>
        name:{{ name || "?"}}
        <br />
        <!-- 子组件 -->
        <input :value="name" @change="handleChange" />
        <br />
        <br />
        <div @click="handleDivClick">
          <button @click="handleClick">重置成功</button>
          <button @click.stop="handleClick">重置失败</button>
        </div>
    </div>
</template>

<script>
export default {
    name: "EventDemo",
    props: {
        name: String
    },
    methods: {
        handleChange(e) {
            this.$emit("change", e.target.value);
            console.log(e)
        },
        handleDivClick() {
            this.$emit("change", "");
            console.log(1)
        },
        handleClick(e) {
            console.log(2)
            console.log(e)
        }
    }
}
</script>