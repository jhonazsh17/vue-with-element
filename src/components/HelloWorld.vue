<template>
  <el-table
    :data="categories"
    style="width: 100%">

    <el-table-column type="expand">
      <template >
        <el-table
          :data="tableData"
          style="width: 100%">
          <el-table-column
            prop="description"
            label="">
          </el-table-column>
          <el-table-column
            prop="amount"
            label="11-05-2020">
          </el-table-column>
          <el-table-column
            prop="amount"
            label="11-05-2020">
          </el-table-column>
          <el-table-column
            prop="amount"
            label="11-05-2020">
          </el-table-column>
          <el-table-column
            prop="amount"
            label="11-05-2020">
          </el-table-column>
          <el-table-column
            prop="amount"
            label="11-05-2020">
          </el-table-column>
          <el-table-column
            prop="address"
            label="Dirección">
          </el-table-column>
        </el-table>
      </template>

    </el-table-column>
    <el-table-column
      prop="name">
    </el-table-column>
    <el-table-column
      prop="amount">
    </el-table-column>
  </el-table>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      categories: [
        {
          id: 1,
          name: 'SALDO INICIAL BANCOS',
        }, 
        {
          id: 2,
          name: 'INGRESOS',
        }, 
        {
          id: 3,
          name: 'SALIDAS',
        }
      ],

      tableData: [{
        description: 'TIENDAS POR DEPARTAMENTO',
        date: '11-05-2020',
        amount: '55.00'
      }, {
        description: 'SAGA FALABELLA SA',
        date: '11-05-2020',
        amount: '100.00'
      }, {
        description: 'HED GROUP SA',
        date: '11-05-2020',
        amount: '120.00'
      }, {
        description: 'BIJOU PERU SOCIEDAD',
        date: '11-05-2020',
        amount: '121.20'
      }, {
        description: 'KOMAX PERU SAC',
        date: '11-05-2020',
        amount: '15.00'
      }, {
        description: 'SUPERMERCADOS PERUANOS',
        date: '11-05-2020',
        amount: '150.00'
      }]
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
