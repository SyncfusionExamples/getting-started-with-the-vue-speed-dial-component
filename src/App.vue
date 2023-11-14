<script setup>
import { SpeedDialComponent as ejsSpeeddial } from "@syncfusion/ej2-vue-buttons";
import { GridComponent as EjsGrid, ColumnsDirective as EColumns, ColumnDirective as EColumn, 
         Edit } from "@syncfusion/ej2-vue-grids";
import { provide, ref } from "vue";
const gridObj = ref(null);
const clicked = function(args)
{
  if(args.item.iconCss == 'e-icons e-plus')
     gridObj.value.ej2Instances.addRecord();
}
const data = [
  {
    OrderID: 10248, CustomerID: 'VINET', EmployeeID: 5, ShipCountry: 'France', Freight: 32.38 
  },
  {
    OrderID: 10249, CustomerID: 'TOMSP', EmployeeID: 6, ShipCountry: 'Germany', Freight: 11.61 
  },
  {
    OrderID: 10250, CustomerID: 'HANAR', EmployeeID: 4, ShipCountry: 'Brazil', Freight: 65.83 
  },
  {
    OrderID: 10251, CustomerID: 'BENTT', EmployeeID: 2, ShipCountry: 'France', Freight: 32.38 
  },
  {
    OrderID: 10252, CustomerID: 'SUSAN', EmployeeID: 3, ShipCountry: 'Germany', Freight: 11.61 
  },
  {
    OrderID: 10253, CustomerID: 'LINDA', EmployeeID: 7, ShipCountry: 'Brazil', Freight: 65.83 
  },
  {
    OrderID: 10254, CustomerID: 'MILLER', EmployeeID: 8, ShipCountry: 'France', Freight: 32.38 
  },
  {
    OrderID: 10255, CustomerID: 'BROWN', EmployeeID: 9, ShipCountry: 'Germany', Freight: 11.61 
  },
  {
    OrderID: 10256, CustomerID: 'DOE', EmployeeID: 11, ShipCountry: 'Brazil', Freight: 65.83 
  }
];
const grid = [Edit];
provide('grid', grid);
const editOptions = { allowAdding : true };

const items = [ { title: "Add", iconCss: "e-icons e-plus" }, 
                { title: "Edit", iconCss: "e-icons e-edit" },
                { title: "Delete", iconCss: "e-icons e-delete" }];
const radialSettings = { direction: "AntiClockwise", offset: "50px" }
const itemTemplateContent = "<div class='itemlist'><span class='icon ${iconCss}' style='padding:3px'></span></div>"
</script>

<template>
<ejsSpeeddial openIconCss="e-icons e-edit" :items="items" target="#target_id"
              position="TopRight" direction="Left" mode="Radial"
              :radialSettings="radialSettings" cssClass="e-outline"
              :itemTemplate="itemTemplateContent" v-on:clicked="clicked"
              modal="true"></ejsSpeeddial>
<ejs-grid id="target_id" :dataSource='data' height="330px" width="700px">
    <e-columns>
      <e-column field='OrderID' width='100' textAlign="Right"></e-column>
      <e-column field='CustomerID' width='100'></e-column>
      <e-column field='EmployeeID' width='100' textAlign="Right"></e-column>
      <e-column field='Freight' width='100' format="C2" textAlign="Right"></e-column>
      <e-column field='ShipCountry' width='100'></e-column>
    </e-columns>
  </ejs-grid>
</template>

<style >
@import "../node_modules/@syncfusion/ej2-icons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-calendars/styles/material.css";
@import "../node_modules/@syncfusion/ej2-dropdowns/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
@import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
@import "../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-grids/styles/material.css";
#target_id
{
  position: relative;
}
.itemlist .text {
  padding: 0 5px;
}

.e-speeddial-li .itemlist {
  display: inherit;
  width: 100%;
  border: 1px solid transparent;
  align-items: center;
  padding: 5px;
  border-radius: 500px;
  background-color: pink;
  box-shadow: 0 0 4px pink;
}

.e-speeddial-li .itemlist:hover {
  background-color:pink;
}
</style>
