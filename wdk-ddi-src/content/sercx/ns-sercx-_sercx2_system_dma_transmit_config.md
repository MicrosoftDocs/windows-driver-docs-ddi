---
UID: NS:sercx._SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG
title: _SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG (sercx.h)
description: The SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new system-DMA-transmit object.
old-location: serports\sercx2_system_dma_transmit_config.htm
tech.root: serports
ms.assetid: AAC70470-B58E-44F1-9CC5-4E0C25539639
ms.date: 04/23/2018
ms.keywords: "*PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, 2/PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, 2/SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure pointer [Serial Ports], SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure [Serial Ports], _SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, serports.sercx2_system_dma_transmit_config"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	2.0\Sercx.h
api_name:
-	SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG, *PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG
---

# _SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure


## -description


The <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new system-DMA-transmit object.


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


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

The translated device address to which the DMA controller transfers data to be transmitted. For more information, see the description of the <b>DeviceAddress</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>.


### -field DmaDescriptor

A pointer to the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the system DMA resource to use for transmit transactions. The serial controller driver gets this structure from the raw resource list it receives in the <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback that starts the serial controller.


### -field MinimumTransferUnitOverride

An override value to use in place of the default minimum transfer unit. The number of bytes specified by an element in a scatter/gather list must be an integer multiple of the minimum transfer unit. A value of  zero indicates that the default minimum transfer unit should be used.  For more information about the default minimum transfer unit, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450995">DMA_ADAPTER_INFO_V1</a>.


### -field Exclusive

Whether to use system-DMA-transmit transactions exclusively to handle write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) requests. Set to <b>TRUE</b> to indicate that write requests should use system-DMA-transmit transactions exclusively. Set to <b>FALSE</b> to indicate that write requests can use a combination of system-DMA-transmit transactions and PIO-transmit transactions.

Set this member to <b>TRUE</b> only if the minimum transfer unit for system-DMA-transmit transactions is one byte, the minimum transaction length is one byte, and the write buffer for the transaction can start on any byte boundary in memory.

If <b>Exclusive</b> is <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>Alignment</b>, and <b>MinimumTransactionLength</b> members must be zero.


### -field EvtSerCx2SystemDmaTransmitInitializeTransaction

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/2B6B33D9-1756-4C0B-91BB-AB36D4B6A913">EvtSerCx2SystemDmaTransmitInitializeTransaction</a> event callbackcallback function.  This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2SystemDmaTransmitCleanupTransaction

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/DAC33D61-F85C-43A7-9F4D-AA31F8CA4430">EvtSerCx2SystemDmaTransmitCleanupTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2SystemDmaTransmitConfigureDmaChannel

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/F5748E93-9761-423B-9971-011FC4D7F6B8">EvtSerCx2SystemDmaTransmitConfigureDmaChannel</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2SystemDmaTransmitDrainFifo

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/796A6C4B-0C7E-43C5-88BC-C03DAA3869A6">EvtSerCx2SystemDmaTransmitDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> and <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> functions.


### -field EvtSerCx2SystemDmaTransmitCancelDrainFifo

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/00B17CBC-FE0E-4611-A41B-42AD833731D3">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> and <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> functions.


### -field EvtSerCx2SystemDmaTransmitPurgeFifo

A pointer to the driver-implemented <a href="https://msdn.microsoft.com/79BD2B77-E99A-4CFA-9F7B-AFC984D5F0B3">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> and <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> functions.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a> method accepts a pointer to a <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2SystemDmaTransmitCreate</b>, call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265345">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450995">DMA_ADAPTER_INFO_V1</a>



<a href="https://msdn.microsoft.com/00B17CBC-FE0E-4611-A41B-42AD833731D3">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="https://msdn.microsoft.com/DAC33D61-F85C-43A7-9F4D-AA31F8CA4430">EvtSerCx2SystemDmaTransmitCleanupTransaction</a>



<a href="https://msdn.microsoft.com/F5748E93-9761-423B-9971-011FC4D7F6B8">EvtSerCx2SystemDmaTransmitConfigureDmaChannel</a>



<a href="https://msdn.microsoft.com/796A6C4B-0C7E-43C5-88BC-C03DAA3869A6">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://msdn.microsoft.com/2B6B33D9-1756-4C0B-91BB-AB36D4B6A913">EvtSerCx2SystemDmaTransmitInitializeTransaction</a>



<a href="https://msdn.microsoft.com/79BD2B77-E99A-4CFA-9F7B-AFC984D5F0B3">EvtSerCx2SystemDmaTransmitPurgeFifo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265345">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547014">WdfDmaEnablerSetMaximumScatterGatherElements</a>
 

 

