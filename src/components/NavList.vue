<template>
    <div class="nav-list-root">
        <div class="nav-list-box">
            <template>
                <div class="nav-list-item"
                     v-for="(item, index) in data"
                     :key="index">
                    <div class="first-item">
                        <span>{{ item.value }}</span>
                        <!-- 这边想做个折叠效果 -->
                        <span v-if="item.children" class="child-arrow" @click="showNavItem"></span>
                    </div>
                    <!-- <i class="child-arrow"></i> -->
                    <div v-if="item.children">
                        <div class="item-child"
                             v-for="(_item, _index) in item.children"
                             :key="_index">
                            {{ _item.value }}
                        </div>
                    </div>
                </div>
            </template>
        </div>
    </div>
</template>
<script>
export default {
    name: 'nav-list',
    props: {
        data: Array
    },
    methods: {
        showNavItem() {}
    }
};
</script>
<style lang="less">
.nav-list-root {
    overflow-y: unset;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    background-color: #fbfafa;
    width: 200px;
    box-shadow: 1px 0 10px #888;
    .nav-list-box {
        padding: 20px;
        .nav-list-item {
            margin: 10px;
        }
        .first-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .item-child {
            margin: 10px;
        }
        .child-arrow {
            display: inline-block;
            margin-bottom: 3px;
            width: 8px;
            height: 8px;
            border-bottom: 1px solid #000;
            border-right: 1px solid #000;
            transform: rotate(45deg);
        }
        /* .child-arrow::before {
            content: '\e6df';
        } */
    }
}
</style>
