<template>
  <v-card class="mx-auto">
    <v-card-title>
      <v-row>
        <v-col>รายการสินค้า</v-col>
        <v-col style="text-aling:right;">
          <!-- <v-card-actions>
              <v-btn icon>
                <v-icon>mdi-bookmark</v-icon>
              </v-btn>
              <v-btn icon>
                <v-icon>mdi-share-variant</v-icon>
              </v-btn>
            </v-card-actions> -->
        </v-col>
      </v-row>
    </v-card-title>
    <v-simple-table
      :dense="false"
      :fixed-header="true"
      :height="450"
    >
      <template v-slot:default>
        <thead>
          <tr>
            <th>Barcode</th>
            <th>Name</th>
            <th>Qty</th>
            <th>Cost</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in tableData" :key="item.GoodsID">
            <th style="font-size: 0.875rem !important;">{{ item.GoodsBarcode }}</th>
            <td>{{ item.GoodsName }}</td>
            <td>{{ item.GoodsQty }}</td>
            <td>{{ item.GoodsCost }}</td>
          </tr>
        </tbody>
      </template>
    </v-simple-table>




    <!-- <table>
      <thead>
        <tr>
          <th>Barcode</th>
          <th>Name</th>
          <th>Qty</th>
          <th>Cost</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in tableData">
          <th>{{ item.GoodsBarcode }}</th>
          <td>{{ item.GoodsName }}</td>
          <td>{{ item.GoodsQty }}</td>
          <td>{{ item.GoodsCost }}</td>
        </tr>
      </tbody>
    </table> -->
    <v-card class="d-flex mb-6" flat tile>
      <v-card-title class="ml-auto" outlined tile>
           <v-pagination
      v-model="page"
      :length="4"
      circle
    ></v-pagination>
      </v-card-title>
    </v-card>
  </v-card>
</template>
<script>
  export default {
    name: 'projects-table',
    props: {
      type: {
        type: String
      },
      title: String
    },
    data() {
      return {
        page: 1,
        tableData: [
          {
            GoodsBarcode: '45862565626',
            GoodsName: 'Argon Design System',
            GoodsQty: '20',
            GoodsCost: '50,000'
          },
          {
            GoodsBarcode: '124125124214124',
            GoodsName: 'React Material Dashboard',
            GoodsQty: '45',
            GoodsCost: '2,500'
          },
          {
            GoodsBarcode: '1845564844',
            GoodsName: 'Black Dashboard',
            GoodsQty: '14',
            GoodsCost: '8,500'
          },
          {
            GoodsBarcode: '1845564844',
            GoodsName: 'Black Dashboard',
            GoodsQty: '14',
            GoodsCost: '8,500'
          },
          {
            GoodsBarcode: '1845564844',
            GoodsName: 'Black Dashboard',
            GoodsQty: '14',
            GoodsCost: '8,500'
          },
          {
            GoodsBarcode: '1845564844',
            GoodsName: 'Black Dashboard',
            GoodsQty: '14',
            GoodsCost: '8,500'
          }
        ]
      }
    }
  }
</script>
<style scoped>
  table {
    width: 100%;
    border-collapse: collapse;
    height: auto;
  }
  
  table thead th {
    background-color: #f6f9fc !important;
    color: #8898aa !important;
  }

  table th {
    padding-top: 0.75rem !important;
    padding-bottom: 0.75rem !important;
    font-size: 0.65rem !important;
    text-transform: uppercase !important;
    letter-spacing: 1px !important;
    text-align: inherit !important;
  }

  table td {
    font-size: 0.8125rem !important;
    white-space: nowrap !important;
    padding: 1rem !important;
  }

  table th, table td {
    padding-left: 1.5rem !important;
    padding-right: 1.5rem !important;
    border-top: 1px solid #e9ecef !important;
    border-bottom: 1px solid #e9ecef !important;
  }
</style>