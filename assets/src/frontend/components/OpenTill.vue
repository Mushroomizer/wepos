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
            var a = window.open('', '', 'height=500, width=500');
            const now = new Date(Date.now()).toUTCString();
            a.document.write('<html>');
            a.document.write('<body >');
            a.document.write(now);
            a.document.write('</body></html>');
            a.document.close();
            a.print();
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