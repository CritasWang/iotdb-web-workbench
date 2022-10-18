<template>
  <div>
    <form-table :form="form"></form-table>
  </div>
</template>
<script>
import { ref } from 'vue';
// import { ElMessage } from 'element-plus';
// import { useI18n } from 'vue-i18n';
import FormTable from '@/components/FormTable';

export default {
  name: 'DeviceMessage',
  setup() {
    // const { t } = useI18n();
    // let erroflag = ref(true);

    const form = ref({
      formData: {
        timeseries: null,
        dataType: null,
        encoding: null,
        description: null,
        alias: null,
        compression: 'SNAPPY',
        tags: [],
        attributes: [],
        display: true,
        border: false,
        namecopy: false,
        seBorder: false,
      },
      formItem: [
        {
          label: 'device.physicalname',
          itemID: 'timeseries',
          type: 'INPUT',
          size: 'small',
          placeholder: 'device.physicalname',
          // event: checkVal,
        },
        {
          label: 'device.alias',
          itemID: 'alias',
          type: 'INPUT',
          size: 'small',
          placeholder: 'device.alias',
          // event: checkValue,
        },
        {
          label: 'device.datatype',
          itemID: 'dataType',
          type: 'SELECT',
          options: [
            { label: 'BOOLEAN', value: 'BOOLEAN' },
            { label: 'INT32', value: 'INT32' },
            { label: 'INT64', value: 'INT64' },
            { label: 'FLOAT', value: 'FLOAT' },
            { label: 'DOUBLE', value: 'DOUBLE' },
            { label: 'TEXT', value: 'TEXT' },
          ],
          // event: changeBorder,
          placeholder: 'device.datatype',
          size: 'small',
        },
        {
          label: 'device.codingmode',
          itemID: 'encoding',
          type: 'SELECTCH',
          required: true,
          size: 'small',
          icon: 'el-icon-question',
        },
        {
          label: 'device.compressionMode',
          itemID: 'compression',
          type: 'SELECT',
          size: 'small',
          icon: 'el-icon-question',
          options: [
            { label: 'UNCOMPRESSED', value: 'UNCOMPRESSED' },
            { label: 'SNAPPY', value: 'SNAPPY' },
            { label: 'LZ4', value: 'LZ4' },
            { label: 'GZIP', value: 'GZIP' },
          ],
        },
        {
          label: 'device.physicaldescr',
          itemID: 'description',
          type: 'TEXT',
          size: 'small',
        },
        {
          label: 'device.tag',
          itemID: 'tags',
          type: 'TAG',
          size: 'small',
        },
        {
          label: 'device.attributes',
          itemID: 'attributes',
          type: 'ATTRIBUTES',
          size: 'small',
        },
      ],
    });

    // function changeBorder() {
    //   form.value.formData.seBorder = false;
    // }
    // function checkValue(scope, object, value, event, item) {
    //   if (value == null || value === '') {
    //     ElMessage.error(`${t('common.placeHolder')}${t(item.label)}`);
    //   } else {
    //     form.value.formData.border = false;
    //   }
    // }
    // function checkVal(scope, obj, val) {
    //   console.log(obj);
    //   if (!/^\w+$/.test(val)) {
    //     if (erroflag.value) {
    //       ElMessage.error(`"${val}"${t('device.pyname')}`);
    //       erroflag.value = false;
    //     }
    //     form.value.formData.border = true;
    //   } else if (val === null || val.length > 255) {
    //     if (erroflag.value) {
    //       ElMessage.error(`"${val}"${t('device.pynamel')}`);
    //       erroflag.value = false;
    //     }
    //     form.value.formData.border = true;
    //   } else {
    //     form.value.formData.border = false;
    //     obj.namecopy = false;
    //   }
    //   setTimeout(() => {
    //     erroflag.value = true;
    //   }, 500);
    // }
    return {
      form,
    };
  },
  components: {
    // StandTable,
    FormTable,
    // ElButton,
    // Echarts,
    // action,
    // ElTabs,
    // ElTabPane,
    // ElDropdown,
    // ElDropdownMenu,
    // ElDropdownItem,
    // ElDialog,
    // ElForm,
    // ElFormItem,
    // ElProgress,
    // EditPhysical,
  },
};
</script>
