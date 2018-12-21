<template>
  <dx-data-grid
    keyExpr="orderId"
    :allowColumnReordering="true"
    :dataSource="sales"
    :selectedRowKeys="selectedKeys"
  >
    <dx-filter-row :visible="true" />
    <dx-group-panel :visible="true" />
    <dx-grouping :autoExpandAll="true" />
    <dx-paging :pageSize="10" />
    <dx-selection mode="multiple" />

    <dx-column
      dataField="orderId"
      caption="Order ID"
      :allowSorting="false"
      :allowFiltering="false"
      :allowGrouping="false"
      :allowReordering:="false"
      :width="100"
    />
    <dx-column dataField="city" />
    <dx-column dataField="country" sortOrder="asc" />
    <dx-column dataField="region" :groupIndex="0" />
    <dx-column
      dataField="date"
      dataType="date"
      selectedFilterOperation=">="
      filterValue="2013/04/01"
      :width="150"
    />
    <dx-column
      dataField="amount"
      format="currency"
      selectedFilterOperation=">="
      :filterValue="1000"
      :width="100"
    />
  </dx-data-grid>
</template>

<script>
import {
  DxDataGrid,
  DxGroupPanel,
  DxGrouping,
  DxPaging,
  DxSelection,
  DxFilterRow,
  DxColumn
} from "devextreme-vue/data-grid";

import { sales, selectedKeys } from "./data.js";

export default {
  components: {
    DxDataGrid,
    DxGroupPanel,
    DxGrouping,
    DxPaging,
    DxSelection,
    DxFilterRow,
    DxColumn
  },
  data() {
    return {
      sales,
      selectedKeys
    };
  }
};
</script>
