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
                    }
                }
            }
        },

        components: {
            Upload,
            Dialog
        },

        beforeCreate() {

        },

        created() {

        },

        beforeMount() {

        },

        mounted() {

        },

        beforeUpdate() {

        },

        updated() {

        },

        beforeDestroy() {

        },

        destroyed() {

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
