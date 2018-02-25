---
UID: NS:sercx._SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG
title: "_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG"
author: windows-driver-content
description: The SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new system-DMA-transmit object.
old-location: serports\sercx2_system_dma_transmit_config.htm
old-project: serports
ms.assetid: AAC70470-B58E-44F1-9CC5-4E0C25539639
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, ,, 2, 2/PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, 2/SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, A, C, D, E, F, G, I, M, N, O, P, PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure pointer [Serial Ports], R, S, SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure [Serial Ports], T, X, Y, _, _SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, serports.sercx2_system_dma_transmit_config"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	2.0\Sercx.h
apiname:
-	SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG
product: Windows
targetos: Windows
req.typenames: SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, *PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG
req.product: Windows 10 or later.
---

# _SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure


## -description


The <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new system-DMA-transmit object.


## -syntax


````
typedef struct _SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG {
  ULONG                                                 Size;
  size_t                                                MaximumTransferLength;
  size_t                                                MinimumTransactionLength;
  ULONG                                                 DmaAlignment;
  ULONG                                                 MaximumScatterGatherFragments;
  DMA_WIDTH                                             DmaWidth;
  PHYSICAL_ADDRESS                                      DeviceAddress;
  PCM_PARTIAL_RESOURCE_DESCRIPTOR                       DmaDescriptor;
  ULONG                                                 MinimumTransferUnitOverride;
  BOOLEAN                                               Exclusive;
  PFN_SERCX2_SYSTEM_DMA_TRANSMIT_INITIALIZE_TRANSACTION EvtSerCx2SystemDmaTransmitInitializeTransaction;
  PFN_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION    EvtSerCx2SystemDmaTransmitCleanupTransaction;
  PFN_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL  EvtSerCx2SystemDmaTransmitConfigureDmaChannel;
  PFN_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO             EvtSerCx2SystemDmaTransmitDrainFifo;
  PFN_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO      EvtSerCx2SystemDmaTransmitCancelDrainFifo;
  PFN_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO             EvtSerCx2SystemDmaTransmitPurgeFifo;
} SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, *PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field MaximumTransferLength

The default maximum size, in bytes, that the serial controller can handle in a single system DMA transfer. If the size of the buffer in the write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request is larger than this maximum size, SerCx2 uses multiple DMA transfers to handle the request, and limits each transfer to the maximum length.


### -field MinimumTransactionLength

The minimum length, in bytes, of a system-DMA-transmit transaction. If the length of the buffer in a write request is less than this minimum length, SerCx2 uses programmed I/O (PIO) for the transaction.


### -field DmaAlignment

DMA alignment requirement. Specifies how the starting address of a transfer in a system-DMA-transmit transaction must be aligned in memory. Set this member to the appropriate FILE_<i>XXX</i>_ALIGNMENT constant in the Wdm.h header file. For example, FILE_WORD_ALIGNMENT indicates that the starting DMA address must be aligned to a two-byte boundary in memory, FILE_LONG_ALIGNMENT indicates that the address must be aligned to a four-byte boundary, and so on. SerCx2 does not support FILE_BYTE_ALIGNMENT. The minimum transfer unit (MTU) of the system DMA adapter should be greater than or equal to the required alignment. For example, if the MTU is four bytes, <b>DmaAlignment</b> must be at least FILE_LONG_ALIGNMENT.


### -field MaximumScatterGatherFragments

The maximum number of buffer fragments that can be specified in the scatter/gather list for a DMA transfer in a system-DMA-transmit transaction.


### -field DmaWidth

The width of the data register at the address specified by <b>DeviceAddress</b>. Possible values are <b>Width8Bits</b>, <b>Width16Bits</b>, <b>Width32Bits</b>, and <b>Width64Bits</b>.


### -field DeviceAddress

The translated device address to which the DMA controller transfers data to be transmitted. For more information, see the description of the <b>DeviceAddress</b> member in <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_system_profile_config.md">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>.


### -field DmaDescriptor

A pointer to the <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the system DMA resource to use for transmit transactions. The serial controller driver gets this structure from the raw resource list it receives in the <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback that starts the serial controller.


### -field MinimumTransferUnitOverride

An override value to use in place of the default minimum transfer unit. The number of bytes specified by an element in a scatter/gather list must be an integer multiple of the minimum transfer unit. A value of  zero indicates that the default minimum transfer unit should be used.  For more information about the default minimum transfer unit, see <a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a>.


### -field Exclusive

Whether to use system-DMA-transmit transactions exclusively to handle write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) requests. Set to <b>TRUE</b> to indicate that write requests should use system-DMA-transmit transactions exclusively. Set to <b>FALSE</b> to indicate that write requests can use a combination of system-DMA-transmit transactions and PIO-transmit transactions.

Set this member to <b>TRUE</b> only if the minimum transfer unit for system-DMA-transmit transactions is one byte, the minimum transaction length is one byte, and the write buffer for the transaction can start on any byte boundary in memory.

If <b>Exclusive</b> is <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>Alignment</b>, and <b>MinimumTransactionLength</b> members must be zero.


### -field EvtSerCx2SystemDmaTransmitInitializeTransaction

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction.md">EvtSerCx2SystemDmaTransmitInitializeTransaction</a> event callbackcallback function.  This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2SystemDmaTransmitCleanupTransaction

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cleanup_transaction.md">EvtSerCx2SystemDmaTransmitCleanupTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2SystemDmaTransmitConfigureDmaChannel

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_configure_dma_channel.md">EvtSerCx2SystemDmaTransmitConfigureDmaChannel</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2SystemDmaTransmitDrainFifo

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> and <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> functions.


### -field EvtSerCx2SystemDmaTransmitCancelDrainFifo

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> and <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> functions.


### -field EvtSerCx2SystemDmaTransmitPurgeFifo

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> and <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> functions.


## -remarks



The <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method accepts a pointer to a <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2SystemDmaTransmitCreate</b>, call the <a href="..\sercx\nf-sercx-sercx2_system_dma_transmit_config_init.md">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize this structure.




## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a>



<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction.md">EvtSerCx2SystemDmaTransmitInitializeTransaction</a>



<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cleanup_transaction.md">EvtSerCx2SystemDmaTransmitCleanupTransaction</a>



<a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a>



<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md">WdfDmaEnablerSetMaximumScatterGatherElements</a>



<a href="..\sercx\nf-sercx-sercx2_system_dma_transmit_config_init.md">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a>



<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_configure_dma_channel.md">EvtSerCx2SystemDmaTransmitConfigureDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

