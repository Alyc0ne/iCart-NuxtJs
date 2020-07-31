<template>
  <div class="content-wrapper">
    <Alert @callBack="callBackValidate" :validateValue="validateValue" />
    <v-row dense>
      <v-col cols="12" lg="9" md="9" sm="12" xs="12">
        <div class="panal-top side-box" style="padding:20px;">
          <v-text-field outlined label="Barcode" :dense="true" prepend-inner-icon="mdi-barcode-scan" v-model="GoodsBarCode" ref="GoodsBarCode"></v-text-field>
          <!-- <input type="text" class="form-control" placeholder="BarCode" name="GoodsBarCode" id="GoodsBarCode" v-model="GoodsBarCode" @change="GetGoodsByBarCode" autofocus> -->
        </div>
        
        <div class="panal-bottom side-box">
          <v-data-table :headers="headers" :items="GoodsInCart" :sort-by="['ListNo']" :sort-desc="[true]" hide-default-footer height="300px">
            <template v-slot:item.GoodsPrice="{ item }">
              <span>{{ item.TotalPrice | FormatComaDecimal}}</span>
            </template>

            <template v-slot:item.TotalPrice="{ item }">
              <span>{{ item.TotalPrice | FormatComaDecimal}}</span>
            </template>

            <template v-slot:item.actions="{ item }">
              <v-icon small @click="deleteItem(item)">
                mdi-delete
              </v-icon>
            </template>
          </v-data-table>
        </div>
      </v-col>


      <v-col cols="12" lg="3" md="3" sm="12" xs="12">
        <div class="panal-top side-box" style="padding:20px;">
          <v-text-field outlined :dense="true" prepend-inner-icon="mdi-account-box"></v-text-field>
          <div class="customer-info">
            <v-card class="mx-auto" max-height="200" outlined>
              <v-card-actions>
                <v-list-item class="grow">
                  <v-list-item-avatar color="grey darken-3">
                    <v-img class="elevation-6" src="https://cdn.vuetifyjs.com/images/cards/store.jpg"></v-img>
                  </v-list-item-avatar>
                  <v-list-item-content style="margin-left:10px;">
                    <v-list-item-title>Evan You</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-card-actions>
            </v-card> 
          </div>
        </div>
        <div class="side-box" style="padding:20px;background-color:#e9ebee;">
          <div class="sub-total" style="width:100%">
            <div class="overflow-text" style="width:40%;float:left;">Sub Total :</div>
            <div class="text-right" style="width:40%;float:right;">0.00</div>
          </div>
          <div class="clean" style="clear:both;margin-bottom:10px;"></div>
          <div class="sub-total" style="width:100%">
            <div class="overflow-text" style="width:40%;float:left;">Discount :</div>
            <div style="width:40%;float:right;" class="text-right">0.00</div>
          </div>
          <div class="clean" style="clear:both;margin-bottom:10px;"></div>
        </div>
        <div class="side-box" style="padding:20px;">
          <div class="sub-total" style="width:100%">
            <div class="overflow-text" style="width:40%;float:left;">Total :</div>
            <div style="width:40%;float:right;" class="text-right">{{ this.CartTotalPrice | FormatComaDecimal }}</div>
          </div>
          <div class="clean" style="clear:both;"></div>
        </div>

        <div class="side-box" style="background-color:#e9ebee;padding:0px;">
          <v-btn style="width:100%;" color="primary" @click="validateTotal">Pay {{ this.CartTotalPrice | FormatComaDecimal }}</v-btn>
        </div>
      </v-col>
    </v-row>
    
    <!-- Grid Item -->
    <!-- <v-row dense>
      <v-col cols="12">
 
      </v-col>
    </v-row> -->
      <!-- <v-footer style="background-color:#e9ebee;">
        <v-spacer></v-spacer>
        <Alert @callBack="callBackValidate" :validateValue="validateValue" />
      </v-footer> -->

  </div>
</template>
<script>
import Alert from '~/components/Shared/Alert.vue'
  export default {
    components: {
      Alert
    },
    data () {
      return {
        e: null,
        validateValue: false,
        headers: [
          {
            text: 'ListNo',
            align: 'center',
            value: 'ListNo',
          },
          { text: 'Name', align: 'left', value: 'GoodsName'},
          { text: 'Code', align: 'left', value: 'GoodsCode' },
          { text: 'Qty', align: 'center', value: 'GoodsQty'},
          { text: 'Price', align: 'right', value: 'GoodsPrice'},
          { text: 'TotalPrice', align: 'right', value: 'TotalPrice'},
          { text: 'Actions', align: 'center', value: 'actions', sortable: false },
        ],
        GoodsInCart: [],
        GoodsBarCode: null,
        Counting: 1,
        CartTotalPrice: 100
      }
    },
    mounted() {
      this.$refs.GoodsBarCode.focus()
      //this.$emit('callAlert', true)
    },
    filters: {
      FormatComaDecimal(amount) {
        const amt = Number(amount)
        return amt.toLocaleString(undefined, {minimumFractionDigits:2})
      }
    },
    methods: {
      GetGoodsByBarCode: function () {
        console.log('kuy')
        this.GoodsInCart.push({
          ListNo: this.Counting,
          GoodsID: 1 + this.Counting,
          GoodsName: "สินค้าทดสอบ",
          GoodsCode: "ITM-00" + this.Counting,
          GoodsQty: this.Counting,
          GoodsPrice: 100 * this.Counting,
          TotalPrice: (100 * this.Counting) * this.Counting,
        })

        this.Counting++
        this.GoodsBarCode = null
      },
      deleteItem: function(item) {
        console.log(item)
      },
      validateTotal: function () {
        this.validateValue = true
      },
      callBackValidate: function (value) {
        this.validateValue = value
      }
    }
  }
</script>