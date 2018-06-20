<template>
		<dx-data-grid
      keyExpr="orderId"
      :allowColumnReordering="true"
      :grouping="grouping"
      :groupPanel="groupPanel"
      :paging="paging"
      :selection="selection"
      :filterRow="filterRow"
      :dataSource="sales"
      :selectedRowKeys="selectedKeys"
      :columns="columns"
			>
		</dx-data-grid>
</template>

<script>
import { DxDataGrid } from "devextreme-vue";
import { sales, selectedKeys } from "./data.js";

export default {
  components: { DxDataGrid },
  data() {
    return {
      sales,
      selectedKeys,
      grouping: { autoExpandAll: true },
      groupPanel: { visible: true },
      paging: { pageSize: 10 },
      selection: { mode: "multiple" },
      filterRow: { visible: true },
      columns: [
        {
          dataField: "orderId",
          caption: "Order ID",
          allowSorting: false,
          allowFiltering: false,
          allowGrouping: false,
          allowReordering: false,
          width: 100
        },
        {
          dataField: "city"
        },
        {
          dataField: "country",
          sortOrder: "asc"
        },
        {
          dataField: "region",
          groupIndex: 0
        },
        {
          dataField: "date",
          dataType: "date",
          selectedFilterOperation: ">=",
          filterValue: "2013/04/01",
          width: 150
        },
        {
          dataField: "amount",
          format: "currency",
          selectedFilterOperation: ">=",
          filterValue: 1000,
          width: 100
        }
      ]
    };
  }
};
</script>
