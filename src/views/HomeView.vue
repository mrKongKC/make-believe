<template>
  <div>
    <div class="rectangle">
      <div class="first-row">
        <span class="text-center border-left-top" style="background-color: #3b3bf7; flex: 1"
          >T</span
        >
        <span class="text-center border-top" style="background-color: #ffffff; flex: 1">E</span>
      </div>
      <div class="second-row">
        <span class="text-center border-bottom-table" style="background-color: #ffffff; flex: 1">S</span>
        <span class="text-center border-bottom-right" style="background-color: #3b3bf7; flex: 1"
          >T</span
        >
      </div>
    </div>
    <Table :columns="columns" :table-data="tableData"></Table>
  </div>
</template>

<script lang="ts" setup>
import Table from '@/components/Table.vue'
const columns = [
  { prop: 'team', label: 'Team' },
  { prop: 'day', label: 'Day' },
  { prop: 'time', label: 'Time' },
  { prop: 'hall', label: 'Hall' }
]

const tableData = [
  {
    team: 'U8 mix',
    day: 'Friday',
    time: [['15:30', '16:45']],
    hall: 'Deusterschule Kitzingen'
  },
  {
    team: 'U10 mix',
    day: ['Friday', 'Friday'],
    time: [
      ['17:00', '18:30'],
      ['16:45', '18:15']
    ],
    hall: ['Deusterschule Kitzingen', 'Deusterschule Kitzingen']
  },
  {
    team: 'U12 mix',
    day: ['Thursday', 'Thursday'],
    time: [
      ['17:35', '18:45'],
      ['11:00', '12:30']
    ],
    hall: ['Mainstockheim', 'Mainstockheim']
  },
  {
    team: 'U14 m',
    day: ['Thursday', 'Thursday'],
    time: [
      ['16:30', '18:30'],
      ['17:00', '18:30']
    ],
    hall: ['Areana Kitzingen', 'Areana Kitzingen']
  },
  {
    team: 'U14 w',
    day: ['Thursday', 'Thursday'],
    time: [
      ['17:00', '18:30'],
      ['18:30', '20:30']
    ],
    hall: ['Areana Kitzingen', 'Areana Kitzingen']
  },
  {
    team: 'U16 m',
    day: ['Thursday', 'Thursday'],
    time: [
      ['16:30', '18:30'],
      ['18:30', '20:00']
    ],
    hall: ['Areana Kitzingen', 'Areana Kitzingen']
  },
  {
    team: 'U18/20 Damon',
    day: ['Thursday', 'Thursday'],
    time: [
      ['18:30', '20:00'],
      ['18:30', '20:30']
    ],
    hall: ['Areana Kitzingen', 'Areana Kitzingen']
  },
  {
    team: 'U18 m',
    day: ['Thursday', 'Thursday'],
    time: [
      ['20:30', '22:00'],
      ['18:30', '20:00']
    ],
    hall: ['Areana Kitzingen', 'Areana Kitzingen']
  },
  {
    team: 'U20 / Men',
    day: ['Sunday', 'Sunday'],
    time: [
      ['20:30', '22:00'],
      ['20:00', '21:30']
    ],
    hall: ['Areana Kitzingen', 'Areana Kitzingen']
  },
  {
    team: 'OPEN COURT',
    day: 'Sunday',
    time: [['15:00', '16:00']],
    hall: 'Areana Kitzingen'
  }
]

const isArray = (data: any) => Array.isArray(data)
</script>

<style>
.text-center {
  text-align: center;
}

.rectangle {
  padding: 8px;
  background-color: #0000ff;
  display: flex;
  flex-direction: column;
  margin-bottom: 40px;
}

.first-row,
.second-row {
  display: flex;
}

.first-row > span,
.second-row > span {
  padding: 12px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.border-left-top {
  border-top: 3px solid #000000;
  border-left: 3px solid #000000;
}

.border-top {
  border-top: 3px solid #000000;
}

.border-bottom-right {
  border-bottom: 3px solid #000000;
  border-right: 3px solid #000000;
}

.border-bottom-table {
  border-bottom: 3px solid #000000 ;
}


tr.el-table__row div.cell,
th.el-table__cell div.cell {
  padding-left: 0 !important;
  padding-right: 0 !important;
}

.divider {
  display: block !important;
}

.none {
  display: none;
}

.flex-center {
  display: flex;
  align-items: center;
}

.justify-center {
  justify-content: center;
}

.justify-around {
  justify-content: space-around;
}

.black-item {
  background-color: #2b2b2b;
  padding: 12px;
  border-radius: 20px;
  color: white;
  margin: 12px 0;
}

.flex-column-center {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.border-bottom {
  border-bottom: 1px solid #ebeef5;
}

.border-bottom:last-child {
  border-bottom: 0px;
}
</style>
