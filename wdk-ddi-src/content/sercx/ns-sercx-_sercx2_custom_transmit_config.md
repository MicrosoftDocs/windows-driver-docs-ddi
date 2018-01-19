---
UID: NS:sercx._SERCX2_CUSTOM_TRANSMIT_CONFIG
title: _SERCX2_CUSTOM_TRANSMIT_CONFIG
author: windows-driver-content
description: The SERCX2_CUSTOM_TRANSMIT_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-transmit object.
old-location: serports\sercx2_custom_transmit_config.htm
old-project: serports
ms.assetid: CC043EA0-391F-48D5-B37D-13136527BFCE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SERCX2_CUSTOM_TRANSMIT_CONFIG, *PSERCX2_CUSTOM_TRANSMIT_CONFIG, SERCX2_CUSTOM_TRANSMIT_CONFIG
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
req.alt-api: SERCX2_CUSTOM_TRANSMIT_CONFIG
req.alt-loc: 2.0\Sercx.h
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
req.typenames: *PSERCX2_CUSTOM_TRANSMIT_CONFIG, SERCX2_CUSTOM_TRANSMIT_CONFIG
req.product: Windows 10 or later.
---

# _SERCX2_CUSTOM_TRANSMIT_CONFIG structure



## -description
The <b>SERCX2_CUSTOM_TRANSMIT_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-transmit object.



## -syntax

````
typedef struct _SERCX2_CUSTOM_TRANSMIT_CONFIG {
  ULONG   Size;
  ULONG   Alignment;
  ULONG   MinimumTransactionLength;
  ULONG   MaximumTransactionLength;
  ULONG   MinimumTransferUnit;
  BOOLEAN Exclusive;
} SERCX2_CUSTOM_TRANSMIT_CONFIG, *PSERCX2_CUSTOM_TRANSMIT_CONFIG;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure. The <a href="..\sercx\nf-sercx-sercx2customtransmitcreate.md">SerCx2CustomTransmitCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field Alignment

Data alignment requirement. Specifies how the starting address of a transfer in a custom-transmit transaction must be aligned in memory. Set this member to the appropriate FILE_<i>XXX</i>_ALIGNMENT constant in the Wdm.h header file. For example, FILE_WORD_ALIGNMENT indicates that the starting address must be aligned to two-byte boundary in memory, FILE_LONG_ALIGNMENT indicates that the address must be aligned to a four-byte boundary, and so on.


### -field MinimumTransactionLength

The minimum length, in bytes, of a data transfer in a custom-transmit transaction. If the length of the buffer in a write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request is less than this minimum length, SerCx2 uses programmed I/O (PIO) for the transaction.


### -field MaximumTransactionLength

The maximum length, in bytes, of a data transfer in a custom-transmit transaction. If the size of the buffer in the write request is larger than this maximum length, SerCx2 uses multiple custom-transmit transactions to handle the request, and limits each transaction to the maximum length.


### -field MinimumTransferUnit

The minimum transfer unit. The number of bytes to transfer in a custom-transmit transaction must be an integer multiple of the minimum transfer unit. To indicate that the default minimum transfer unit should be used, set this member to zero. For more information about the default minimum transfer unit, see <a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a>.


### -field Exclusive

Whether to use custom-transmit transactions exclusively to handle write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) requests. Set to <b>TRUE</b> to indicate that write requests should use custom-transmit transactions exclusively. Set to <b>FALSE</b> to indicate that write requests can use a combination of custom-transmit transactions and PIO-transmit transactions.

Set this member to <b>TRUE</b> only if the minimum transfer unit for custom-transmit transactions is one byte, the minimum transaction length is one byte, and the write buffer for the transaction can start on any byte boundary in memory.

If <b>Exclusive</b> is <b>TRUE</b>, the <b>MinimumTransferUnit</b>, <b>Alignment</b>, and <b>MinimumTransactionLength</b> members must be zero.


## -remarks
The <a href="..\sercx\nf-sercx-sercx2customtransmitcreate.md">SerCx2CustomTransmitCreate</a> method accepts a pointer to a <b>SERCX2_CUSTOM_TRANSMIT_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2CustomTransmitCreate</b>, call the <a href="..\sercx\nf-sercx-sercx2_custom_transmit_config_init.md">SERCX2_CUSTOM_TRANSMIT_CONFIG_INIT</a> function to initialize this structure.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2_custom_transmit_config_init.md">SERCX2_CUSTOM_TRANSMIT_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2customtransmitcreate.md">SerCx2CustomTransmitCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_CUSTOM_TRANSMIT_CONFIG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

