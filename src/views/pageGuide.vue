<template>
    <div class="page">
        <div class="div1">demo</div>
    </div>
</template>

<script>
    import Upload from '@/components/Plupload'
    import Dialog from '@/components/Dialog'

    export default {

        data() {
            return {
                autoConfig: {
                    searchForm: {
                        isPrice: false,
                        checkMyLove: []
                    },
                    query: [{
                        type: 'radio',
                        title: '是否收费',
                        key: 'isPrice',
                        data: [
                            {
                                title: '免费',
                                key: 'name'
                            },{
                                title: '收费',
                                key: 'name'
                            },
                        ]
                    },{
                        type: 'checkbox',
                        title: '选择喜欢的类型',
                        key: 'checkMyLove',
                        data: [
                            {
                                title: '可爱的',
                                key: 'name'
                            },{
                                title: '幽默的',
                                key: 'name'
                            },{
                                title: '睿智的',
                                key: 'name'
                            },
                        ]
                    },{
                        type: 'textbox',
                        title: '姓名',
                        key: 'name'
                    },
                        {
                            type: 'select',
                            title: '城市',
                            key: 'city',
                            data: [
                                {
                                    title: '北京',
                                    key: 'name',
                                    val: 'beijing'
                                },
                                {
                                    title: '上海',
                                    key: 'name',
                                    val: 'shanghai'
                                }
                            ]
                        },{
                            type: 'timeHorizon',
                            title: '时间',
                            key: 'name',
                            data: [
                                {
                                    keyTitle: '开始时间',
                                    keyName: 'fromDate'
                                },
                                {
                                    keyTitle: '结束时间',
                                    keyName: 'endDate'
                                }
                            ]
                        },{
                            type: 'btn',
                            title: '搜索'
                        }],

                    table: {
                        headers: [{
                            title: '日期',
                            key: 'date',
                        },{
                            title: '姓名',
                            key: 'name',
                        },{
                            title: '地址',
                            key: 'address',
                        }],
                        itemAction: [{
                            title: '查看',
                            action: 'read'
                        },{
                            title: '编辑',
                            action: 'edit'
                        },{
                            title: '删除',
                            action: 'del'
                        }],
                    },

                    api: {
                        add: 'news/add',
                        del: 'news/del',
                        update: 'news/update',
                        search: 'news/search',
                    }
                },
            }
        },

        components: {
            Upload,
            Dialog
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

        // 自定义各种方法
        methods: {
            add() {

            },
            del() {

            },
            edit() {
                // Vue.nextTick( [callback, context] )：
                // 在下次 DOM 更新循环结束之后执行延迟回调。在修改数据之后立即使用这个方法，获取更新后的 DOM。
                this.nextTick(() => {
                    // doSomething
                })
            }
        }

    }
</script>

<style lang="scss" scoped>
    .page {
        .div1 {
            font-size: 12px;
        }
    }
</style>
