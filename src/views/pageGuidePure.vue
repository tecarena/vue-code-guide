<template>
    <div class="pageGuidePure">
        <div class="div1">demo</div>
        {{ message | capitalize }}
        <p>FullName: {{fullName}}</p>
        <p>FirstName: <input type="text" v-model="firstName"></p>
    </div>
</template>

<script>
    import Upload from '@/components/Plupload'
    import Dialog from '@/components/Dialog'

    export default {

        name: 'pageGuidePure',

        extends: {},

        props: {
            city: {}, // 按字母顺序
            foo: {},
            good: {},
        },

        data() {
            return {
                autoConfig: {
                    searchForm: {
                        isPrice: false,
                        checkMyLove: []
                    }
                },
                message: 'hello',
                firstName: 'Lucy',
                lastName: 'roboter',
                fullName: ''
            }
        },

        computed: {},

        components: {
            Upload,
            Dialog
        },

        filters: {
            capitalize: function (value) {
                if (!value) return ''
                value = value.toString()
                return value.charAt(0).toUpperCase() + value.slice(1)
            }
        },
        watch: {
            // watch代码的效果是，当我们输入firstName后，wacth监听每次修改变化的新值，然后计算输出fullName。
            firstName(newName, oldName) {
                this.fullName = newName + ' ' + this.lastName;
            },
            secondChange:{
                handler(oldVal,newVal){
                    console.log(oldVal)
                    console.log(newVal)
                },
                deep:true
            }
        },

        methods: {
            add() {

            },

            del() {

            },

            edit() {
                this.nextTick(() => {
                    // doSomething
                })
            }
        },

        // S 生命周期方法 从实例创建前到实例被销毁
        beforeCreate() {
            // 实例被创建之前执行
        },
        created() {
            // 实例已经创建完成之后执行
        },
        beforeMount() {
            // 载入前（完成了data和el数据初始化），
            // 但是页面中的内容还是vue中的占位符，
            // data中的message信息没有被挂在到Bom节点中，
            // 在这里可以在渲染前最后一次更改数据的机会，
            // 不会触发其他的钩子函数，一般可以在这里做初始数据的获取
        },
        mounted() {
            // 将编译好的html挂载到页面 完成后执行的钩子函数，
            // 此时可以进行发送ajax请求获取数据的操作进行数据初始化
            // 注意：mounted在整个实例生命周期内只执行一次
        },
        beforeUpdate() {
            // 数据更新时调用，发生在虚拟 DOM 重新渲染和打补丁之前。
            // 你可以在这个钩子中进一步地更改状态，
            // 这不会触发附加的重渲染过程。
            // 当我们更改Vue的任何数据，都会触发该函数
        },
        updated() {
            // 数据已经更改完成，dom也重新render完成
        },
        beforeDestroy() {
            // 销毁前执行（$destroy方法被调用的时候就会执行）,
            // 一般在这里善后:清除计时器、清除非指令绑定的事件等等’)
        },
        destroyed() {
            // Vue 实例销毁后调用。调用后，Vue 实例指示的所有东西都会解绑定，所有的事件监听器会被移除，所有的子实例也会被销毁。
            // 该钩子在服务器端渲染期间不被调用。
        },
        // E 生命周期方法



    }
</script>

<style lang="scss" scoped>
    .pageGuidePure {
        .div1 {
            font-size: 12px;
        }
    }
</style>
