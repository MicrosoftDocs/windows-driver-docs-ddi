---
UID: NS:sercx._SERCX2_CUSTOM_RECEIVE_CONFIG
title: "_SERCX2_CUSTOM_RECEIVE_CONFIG"
author: windows-driver-content
description: The SERCX2_CUSTOM_RECEIVE_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-receive object.
old-location: serports\sercx2_custom_receive_config.htm
old-project: serports
ms.assetid: 815DB069-4AB5-4C00-BB7A-BAAA4050C8CF
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PSERCX2_CUSTOM_RECEIVE_CONFIG, 2/PSERCX2_CUSTOM_RECEIVE_CONFIG, 2/SERCX2_CUSTOM_RECEIVE_CONFIG, PSERCX2_CUSTOM_RECEIVE_CONFIG, PSERCX2_CUSTOM_RECEIVE_CONFIG structure pointer [Serial Ports], SERCX2_CUSTOM_RECEIVE_CONFIG, SERCX2_CUSTOM_RECEIVE_CONFIG structure [Serial Ports], _SERCX2_CUSTOM_RECEIVE_CONFIG, serports.sercx2_custom_receive_config"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	2.0\Sercx.h
api_name:
-	SERCX2_CUSTOM_RECEIVE_CONFIG
product: Windows
targetos: Windows
req.typenames: SERCX2_CUSTOM_RECEIVE_CONFIG, *PSERCX2_CUSTOM_RECEIVE_CONFIG
---

# _SERCX2_CUSTOM_RECEIVE_CONFIG structure


## -description


The <b>SERCX2_CUSTOM_RECEIVE_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new custom-receive object.


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265248">SerCx2CustomReceiveCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field Alignment

Data alignment requirement. Specifies how the starting address of a transfer in a custom-receive transaction must be aligned in memory. Set this member to the appropriate FILE_<i>XXX</i>_ALIGNMENT constant in the Wdm.h header file. For example, FILE_WORD_ALIGNMENT indicates that the starting address must be aligned to two-byte boundary in memory, FILE_LONG_ALIGNMENT indicates that the address must be aligned to a four-byte boundary, and so on.


### -field MinimumTransactionLength

The minimum length, in bytes, of a data transfer in a custom-receive transaction. If the length of the buffer in a read (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>) request is less than this minimum length, SerCx2 uses programmed I/O (PIO) for the transaction.


### -field MaximumTransactionLength

The maximum length, in bytes, of a data transfer in a custom-receive transaction. If the size of the buffer in the read request is larger than this maximum length, SerCx2 uses multiple custom-receive transactions to handle the request, and limits each transaction to the maximum length.


### -field MinimumTransferUnit

The minimum transfer unit. The number of bytes specified by an element in a scatter/gather list must be an integer multiple of the minimum transfer unit. To indicate that the default minimum transfer unit should be used, set this member to zero. For more information about the default minimum transfer unit, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450995">DMA_ADAPTER_INFO_V1</a>.


### -field Exclusive

Whether to use custom-receive transactions exclusively to handle write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>) requests. Set to <b>TRUE</b> to indicate that read requests should use custom-receive transactions exclusively. Set to <b>FALSE</b> to indicate that read requests can use a combination of custom-receive transactions and PIO-receive transactions.

Set this member to <b>TRUE</b> only if the minimum transfer unit for custom-receive transactions is one byte, the minimum transaction length is one byte, and the read buffer for the transaction can start on any byte boundary in memory.

If <b>Exclusive</b> is <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>Alignment</b>, and <b>MinimumTransactionLength</b> members must be zero.

Regardless of the value of this member, PIO-receive transactions are used to save any unread data in the receive FIFO before the serial controller exits the D0 device power state to enter a low-power state.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/dn265248">SerCx2CustomReceiveCreate</a> method accepts a pointer to a <b>SERCX2_CUSTOM_RECEIVE_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2CustomReceiveCreate</b>, call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265313">SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</a> function to initialize this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450995">DMA_ADAPTER_INFO_V1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265313">SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265248">SerCx2CustomReceiveCreate</a>
 

 

