<template>
    <div class="alert">
        <div class="blackdrop-alert box" :class="ListvalidateValue ? 'show':'hide'"></div>
        <div class="justify-center" style="100%;">
            <v-alert type="error" border="top" colored-border elevation="2" style="width:50%;position:absolute;z-index:100;margin:0% 0% 0% 0%;" :class="ListvalidateValue ? 'show':'hide'" :dismissible="true">
                <v-list-item>
                    <v-list-item-content>
                        <v-list-item-title>ไม่สามารถดำเนินการได้</v-list-item-title>
                        <v-list-item-subtitle>เนื่องจากยังไม่มีสินค้า : {{ ListvalidateValue }}</v-list-item-subtitle>
                    </v-list-item-content>
                </v-list-item>
            </v-alert>
        </div>
    </div>
</template>>
<script>
export default {
    props: ['validateValue'],
    data () {
        return {
            ListvalidateValue: this.validateValue
        }
    },
    mounted() {
      //console.log(this.validateValue)
    },
    watch: {
        validateValue: {
            handler: function(val, oldVal) {
                this.ListvalidateValue = this.validateValue
                setTimeout(() => {
                    //this.$emit('callBack', false);
                }, 3000)
            },
            deep: true
        }
    },      

    methods: {

    }
}
</script>
<style  scoped>
.show {
    display: block;
}
.hide {
    display: none;
}
.box {
  background:#e9ebee;
  position:absolute;
  top:0px;
  right:0px;
  bottom:0px;
  left:0px;
  z-index: 90;
  opacity: 0.8;
}
</style>