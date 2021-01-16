---
UID: NS:sercx._SERCX2_SYSTEM_DMA_RECEIVE_CONFIG
title: _SERCX2_SYSTEM_DMA_RECEIVE_CONFIG (sercx.h)
description: The SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new system-DMA-receive object.
old-location: serports\sercx2_system_dma_receive_config.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure"]
ms.keywords: "*PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG, 2/PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG, 2/SERCX2_SYSTEM_DMA_RECEIVE_CONFIG, PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG, PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure pointer [Serial Ports], SERCX2_SYSTEM_DMA_RECEIVE_CONFIG, SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure [Serial Ports], _SERCX2_SYSTEM_DMA_RECEIVE_CONFIG, serports.sercx2_system_dma_receive_config"
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SERCX2_SYSTEM_DMA_RECEIVE_CONFIG, *PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG
f1_keywords:
 - _SERCX2_SYSTEM_DMA_RECEIVE_CONFIG
 - sercx/_SERCX2_SYSTEM_DMA_RECEIVE_CONFIG
 - PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG
 - sercx/PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG
 - SERCX2_SYSTEM_DMA_RECEIVE_CONFIG
 - sercx/SERCX2_SYSTEM_DMA_RECEIVE_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 2.0\Sercx.h
api_name:
 - _SERCX2_SYSTEM_DMA_RECEIVE_CONFIG
 - PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG
 - SERCX2_SYSTEM_DMA_RECEIVE_CONFIG
---

# _SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure


## -description

The <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new system-DMA-receive object.

## -struct-fields

### -field Size

The size, in bytes, of this structure. The <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

### -field MaximumTransferLength

The default maximum size, in bytes, that the serial controller can handle in a single system DMA transfer. If the size of the buffer in the read (<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>) request is larger than this maximum size, SerCx2 uses multiple DMA transfers to handle the request, and limits each transfer to the maximum length.

### -field MinimumTransactionLength

The minimum length, in bytes, of a system-DMA-receive transaction. If the length of the buffer in a read request is less than this minimum length, SerCx2 uses programmed I/O (PIO) for the transaction.

### -field DmaAlignment

DMA alignment requirement. Specifies how the starting address of a transfer in a system-DMA-receive transaction must be aligned in memory. Set this member to the appropriate FILE_<i>XXX</i>_ALIGNMENT constant in the Wdm.h header file. For example, FILE_WORD_ALIGNMENT indicates that the starting DMA address must be aligned to two-byte boundary in memory, FILE_LONG_ALIGNMENT indicates that the address must be aligned to a four-byte boundary, and so on. SerCx2 does not support FILE_BYTE_ALIGNMENT. The minimum transfer unit (MTU) of the system DMA adapter should be greater than or equal to the required alignment. For example, if the MTU is four bytes, <b>DmaAlignment</b> must be at least FILE_LONG_ALIGNMENT.

### -field MaximumScatterGatherFragments

The maximum number of buffer fragments that can be specified in the scatter/gather list for a DMA transfer in a system-DMA-receive transaction.

### -field DmaWidth

The width of the data register at the address specified by <b>DeviceAddress</b>. Possible values are <b>Width8Bits</b>, <b>Width16Bits</b>, <b>Width32Bits</b>, and <b>Width64Bits</b>.

### -field DeviceAddress

The translated address from which the DMA controller transfers. For more information, see the description of the <b>DeviceAddress</b> member in <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_system_profile_config">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>.

### -field DmaDescriptor

A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the system DMA resource to use for receive transactions. The serial controller driver gets this structure from the raw resource list it receives in the <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback that starts the serial controller.

### -field MinimumTransferUnitOverride

An override value to use in place of the default minimum transfer unit. The number of bytes specified by an element in a scatter/gather list must be an integer multiple of the minimum transfer unit. A value of zero indicates that the default minimum transfer unit should be used. For more information, see the description of the <b>MinimumTransferUnit</b> member in <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter_info_v1">DMA_ADAPTER_INFO_V1</a>.

### -field Exclusive

Whether to use system-DMA-receive transactions exclusively to handle write (<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>) requests. Set to <b>TRUE</b> to indicate that read requests should use system-DMA-receive transactions exclusively. Set to <b>FALSE</b> to indicate that read requests can use a combination of system-DMA-receive transactions and PIO-receive transactions.

Set this member to <b>TRUE</b> only if the minimum transfer unit for system-DMA-receive transactions is one byte, the minimum transaction length is one byte, and the read buffer for the transaction can start on any byte boundary in memory.

If <b>Exclusive</b> is <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>DmaAlignment</b>, and <b>MinimumTransactionLength</b> members must be zero.

Regardless of the value of this member, PIO-receive transactions are used to save any unread data in the receive FIFO before the serial controller exits the D0 device power state to enter a low-power state.

### -field EvtSerCx2SystemDmaReceiveInitializeTransaction

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction">EvtSerCx2SystemDmaReceiveInitializeTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field EvtSerCx2SystemDmaReceiveCleanupTransaction

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction">EvtSerCx2SystemDmaReceiveCleanupTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field EvtSerCx2SystemDmaReceiveConfigureDmaChannel

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_configure_dma_channel">EvtSerCx2SystemDmaReceiveConfigureDmaChannel</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field EvtSerCx2SystemDmaReceiveEnableNewDataNotification

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement an <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function.

### -field EvtSerCx2SystemDmaReceiveCancelNewDataNotification

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement an <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function.

## -remarks

The <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method accepts a pointer to a <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2SystemDmaReceiveCreate</b>, call the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_system_dma_receive_config_init">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a> or <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_system_dma_receive_config_init_new_data_notification">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a> function to initialize this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction">EvtSerCx2SystemDmaReceiveCleanupTransaction</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_configure_dma_channel">EvtSerCx2SystemDmaReceiveConfigureDmaChannel</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction">EvtSerCx2SystemDmaReceiveInitializeTransaction</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_system_dma_receive_config_init">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_system_dma_receive_config_init_new_data_notification">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements">WdfDmaEnablerSetMaximumScatterGatherElements</a>

