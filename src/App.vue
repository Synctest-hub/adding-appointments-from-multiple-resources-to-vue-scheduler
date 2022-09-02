<template>
    <ejs-schedule height="600px" :selectedDate='schedulerSelectedDate' 
      :eventSettings="appointmentData">
      <e-resources>
        <e-resource :dataSource="resourceDatasource" field="ResourceId" title="Resources"
        name="ResourceName" textField="personName" idField="personId" colorField="color"
        allowMultiple="true">
        </e-resource>
      </e-resources>
    </ejs-schedule>
</template>

<script> 
import { ScheduleComponent, Day, WorkWeek, Week, Month, Agenda, ResourcesDirective, ResourceDirective } from "@syncfusion/ej2-vue-schedule";
export default {
  name: 'App',
  components: { 
    'ejs-schedule': ScheduleComponent,
    'e-resources' : ResourcesDirective, 
    'e-resource' : ResourceDirective 
  },
  provide : { schedule : [ Day, WorkWeek, Week, Month, Agenda] },
  data() {
    return {
      schedulerSelectedDate : new Date(2022, 5, 6),
      resourceDatasource : [
        {personName: 'John', personId: 1, color: '#ea7a57'},
        {personName: 'Steve', personId: 2, color: '#357CD2'},
        {personName: 'James', personId: 3, color: '#7fa900'}
      ],
      appointmentData : {
         dataSource : [
             {
              Id : 1,
              Subject : 'Skarting',
              StartTime: new Date(2022, 5, 6, 10, 0, 0),
              EndTime: new Date(2022, 5, 6, 11, 0, 0),
              ResourceId : 1
            },
            {
              Id : 2,
              Subject : 'Swimming',
              StartTime: new Date(2022, 5, 9, 10, 30, 0),
              EndTime: new Date(2022, 5, 9, 11, 30, 0),
              ResourceId : 2
            },
            {
              Id : 3,
              Subject : 'Table Tennis',
              StartTime: new Date(2022, 5, 7, 12, 0, 0),
              EndTime: new Date(2022, 5, 7, 13, 0, 0),
              ResourceId : 3
            }
         ]
      }
    };
  }
}
</script>

<style>
  @import '../node_modules/@syncfusion/ej2-base/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-buttons/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-calendars/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-dropdowns/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-inputs/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-navigations/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-popups/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-vue-schedule/styles/material.css';
</style>
