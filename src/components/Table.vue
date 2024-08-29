<template>
  <el-table :data="tableData" style="width: 100%" stripe>
    <el-table-column
      v-for="column in columns"
      :key="column.prop"
      :prop="column.prop"
      :label="column.label"
    >
      <template #default="scoped">
        <div v-if="isArray(scoped.row[column.prop])" class="flex-column-center">
          <div v-for="(item, index) in scoped.row[column.prop]" :key="index" class="border-bottom">
            <div v-if="isArray(item)" class="flex-center" style="gap: 12px">
              <span
                v-for="(inItem, index) in item"
                :key="index"
                class="flex-center"
                style="gap: 12px"
              >
                <p class="black-item">{{ inItem }}</p>
                <span class="none" :class="{ divider: index !== item.length - 1 }">-</span>
              </span>
            </div>
            <p v-else>{{ item }}</p>
          </div>
        </div>
        <p v-else>{{ scoped.row[column.prop] }}</p>
      </template>
    </el-table-column>
  </el-table>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

defineProps<{
  tableData: any[],
  columns: any[]
}>()

const isArray = (data: any) => Array.isArray(data)
</script>

<style>
tr.el-table__row div.cell,
th.el-table__cell div.cell {
  padding-left: 0 !important;
  padding-right: 0 !important;
}

.divider{
  display: block !important;
}

.none{
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
