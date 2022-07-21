<template>
    <div class="wepos-open-till-wrap" v-hotkey="hotkeys">
        <a href="#" @click.prevent="openTill">{{ __('Open Till', 'wepos') }}</a>
    </div>
</template>

<script>
export default {
    data() {
        return {}
    },
    computed: {
        hotkeys() {
            return {}
        }
    },
    methods: {
        openTill(e) {
            e.preventDefault();
            this.printTime();
        },
        printTime() {
            var a = window.open('', '', 'height=400, width=300');
            const now = new Date(Date.now()).toUTCString();
            a.document.write('<html>');
            a.document.write('<body >');
            a.document.write(now);
            a.document.write('</body></html>');
            a.document.close(); // necessary for IE >= 10
            a.focus(); // necessary for IE >= 10*/

            a.print();
            a.close();

            return true;
        }
    }
};
</script>

<style lang="less">
.wepos-open-till-wrap {
    float: left;
    display: inline-block
}
</style>