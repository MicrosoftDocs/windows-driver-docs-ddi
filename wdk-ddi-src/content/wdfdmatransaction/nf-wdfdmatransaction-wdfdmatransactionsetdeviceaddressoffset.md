---
UID: NF:wdfdmatransaction.WdfDmaTransactionSetDeviceAddressOffset
title: WdfDmaTransactionSetDeviceAddressOffset function
author: windows-driver-content
description: The WdfDmaTransactionSetDeviceAddressOffset method specifies the offset of the register that the system DMA controller will access when performing the DMA operation.
old-location: wdf\wdfdmatransactionsetdeviceaddressoffset.htm
old-project: wdf
ms.assetid: A45231E0-0807-41AA-B20F-6335067BE99A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDmaTransactionSetDeviceAddressOffset, WdfDmaTransactionSetDeviceAddressOffset method, kmdf.wdfdmatransactionsetdeviceaddressoffset, wdf.wdfdmatransactionsetdeviceaddressoffset, wdfdmatransaction/WdfDmaTransactionSetDeviceAddressOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaTransactionSetDeviceAddressOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionSetDeviceAddressOffset function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WdfDmaTransactionSetDeviceAddressOffset</b> method specifies the offset of the register that the system DMA controller will access when performing the DMA operation.


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that specifies the transaction to modify.


### -param Offset [in]

The offset of the register, from the <b>DeviceAddress</b> specified in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>, to or from which DMA should be performed.


## -returns



This method does not return a value.




## -remarks



<b>WdfDmaTransactionSetDeviceAddressOffset</b> must be used with a DMA enabler that specifies a system-mode DMA profile.

Framework-based drivers call <b>WdfDmaTransactionSetDeviceAddressOffset</b> after initializing a DMA transaction and before executing it.

A driver can use this method to access multiple registers within a device's register file.

For example, a driver might use DMA to access separate read and write registers in a device's register file.

To do so, the driver specifies the base address of the device's register file when configuring the enabler, and then sets the offset of the read or write register as necessary before executing the transaction.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.


#### Examples

The following code example initializes a DMA transaction.  It then sets the offset of the register that the system DMA controller will access, provides a transfer completion callback routine, and executes the DMA transaction.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfDmaTransactionInitialize(
                                     RequestContext-&gt;DmaTransaction,
                                     EvtProgramDma,
                                     direction,
                                     mdl,
                                     startingVa,
                                     length
                                     );

if(!NT_SUCCESS(status)) {
    goto Complete;
}

WdfDmaTransactionSetDeviceAddressOffset(
                                        RequestContext-&gt;DmaTransaction,
                                        READ_DATA_REGISTER_OFFSET
                                        );

WdfDmaTransactionSetTransferCompleteCallback(
                                             RequestContext-&gt;DmaTransaction,
                                             EvtDmaTransactionDmaTransferComplete,
                                             RequestContext
                                             );

status = WdfDmaTransactionExecute(
                                  RequestContext-&gt;DmaTransaction, 
                                  RequestContext );

if(!NT_SUCCESS(status)) {
    goto Complete;
}

return status;

Complete:

WdfDmaTransactionRelease(
                         RequestContext-&gt;DmaTransaction
                         );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>
 

 

