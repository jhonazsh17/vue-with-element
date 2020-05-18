<template>
  <div>
    <div class="container">
      <div class="block">
        <el-date-picker
          @change="changeDay()"
          v-model="value2"
          type="date"
          placeholder="Pick a day">
        </el-date-picker>
      </div>  
    </div> 

    <el-table
      :data="items"
      style="width: 100%">

      <el-table-column type="expand" >
        
        <!-- Tabla dentro de partida general - @jhonazsh -->
        <template slot-scope="props" v-if="props.row.subItems.length>0">
          <el-table
            :data="props.row.subItems"
            style="width: 100%"
            :show-header="false">

            <el-table-column 
            type="expand">

              <!-- table childs -->
              <template slot-scope="props" v-if="props.row.childs.length>0">
                <el-table
                  :data="props.row.childs"
                  style="width: 100%"
                  :show-header="false">
                  <el-table-column
                    type="index">
                  </el-table-column>
                  <el-table-column
                    prop="description"
                    label="">
                  </el-table-column>
                  <el-table-column
                    prop="amount">
                  </el-table-column>
                </el-table>
              </template>
              <!-- Fin -->

            </el-table-column>

            <el-table-column
              prop="description">
            </el-table-column>
            <el-table-column
              prop="amount">
            </el-table-column>
          </el-table>

        </template>
        <!-- Fin -->

      </el-table-column>
      <el-table-column 
        
        prop="name">
      </el-table-column>
      <el-table-column
        label="daySearch"
        prop="amount">
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      items: [
        {
          id: 1,
          name: 'SALDO INICIAL BANCOS',
          amount: 'S/. 213,725.00',
          subItems: [],
          expand: false,
            
        },{
          id: 2,
          name: 'INGRESOS',
          amount: 'S/. 262,851.00',
          subItems: [ 
            {
              description: 'TIENDAS POR DEPARTAMENTO',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            },
            {
              description: 'SAGA FALABELLA SA',
              date: '11-05-2020',
              amount: 'S/. 850.00',
              childs: []
            },
            {
              description: 'HED GROUP S.A.C.',
              date: '11-05-2020',
              amount: 'S/. 1,416.00',
              childs: []
            },
            {
              description: 'BIJOU PERU SOCIEDAD',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            },
            {
              description: 'KOMAX PERU SAC',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            },
            {
              description: 'SUPERMERCADOS PERUANOS',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            },
            {
              description: 'MENDOZA BARBARAN MAR',
              date: '11-05-2020',
              amount: 'S/. 212.00',
              childs: []
            },
            {
              description: 'NEW ATHLETIC GROUP SAC',
              date: '11-05-2020',
              amount: 'S/. 71.00',
              childs: []
            },
            {
              description: 'MANUFACTURA BOLIVIAN',
              date: '11-05-2020',
              amount: 'S/. 302.00',
              childs: []
            },
            {
              description: 'POR FACTURAR',
              date: '11-05-2020',
              amount: 'S/. 60,000.00',
              childs: []
            },
            {
              description: 'COBRO DE VENTAS ESTIMADAS',
              date: '11-05-2020',
              amount: 'S/. 200,000.00',
              childs: []
            }
          ]
        },{
          id: 3,
          name: 'SALIDAS',
          amount: 'S/. 416,180.00',
          subItems: [  
            {
              description: 'PROVEEDORES',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: [
                {
                  description: 'VELEZ BURGOS NARCISO',
                  date: '11-05-2020',
                  amount: 'S/. 5,153.00',
                },
                {
                  description: 'MOBILIA INDUSTRIAL SA',
                  date: '11-05-2020',
                  amount: 'S/. 997.00',
                }
              ]
            },
            {
              description: 'IMPUESTOS',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            },
            {
              description: 'BANCOS',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            },
            {
              description: 'PERSONAL',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            },
            {
              description: 'PAGOS VARIOS',
              date: '11-05-2020',
              amount: 'S/. 0.00',
              childs: []
            }
          ]
        }, 
          {
            id: 4,
            name: 'SALDO FLUJO ECONÓMICO',
            amount: 'S/. 60,396.00',
            subItems: []
          }, 
          {
            id: 5,
            name: 'FINANCIAMIENTO',
            amount: 'S/. 0.00',
            subItems: []
          }, 
          {
            id: 6,
            name: 'SALDO FLUJO FINANCIERO',
            amount: 'S/. 60,396.00',
            subItems: []
          }  
      ],
      options: [{
          value: 'Option1',
          label: 'Option1'
        }, {
          value: 'Option2',
          label: 'Option2'
        }, {
          value: 'Option3',
          label: 'Option3'
        }, {
          value: 'Option4',
          label: 'Option4'
        }, {
          value: 'Option5',
          label: 'Option5'
        }],
      value: '',
      value2: "",
      daySearch: "",
      alignItem: "text-align: center"
    }
  },
  methods: {
    changeDay(){
      console.log(this.value2);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
</style>
