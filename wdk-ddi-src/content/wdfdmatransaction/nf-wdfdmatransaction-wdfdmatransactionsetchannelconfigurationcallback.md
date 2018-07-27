---
UID: NF:wdfdmatransaction.WdfDmaTransactionSetChannelConfigurationCallback
title: WdfDmaTransactionSetChannelConfigurationCallback function
author: windows-driver-content
description: The WdfDmaTransactionSetChannelConfigurationCallback method registers a channel configuration event callback function for a system-mode DMA transaction.
old-location: wdf\wdfdmatransactionsetchannelconfigurationcallback.htm
tech.root: wdf
ms.assetid: B38BD937-5027-4EED-9ECA-3333F56DFFA8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDmaTransactionSetChannelConfigurationCallback, WdfDmaTransactionSetChannelConfigurationCallback method, kmdf.wdfdmatransactionsetchannelconfigurationcallback, wdf.wdfdmatransactionsetchannelconfigurationcallback, wdfdmatransaction/WdfDmaTransactionSetChannelConfigurationCallback
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
-	WdfDmaTransactionSetChannelConfigurationCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionSetChannelConfigurationCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The <b>WdfDmaTransactionSetChannelConfigurationCallback</b> method registers a channel configuration event callback function for a system-mode DMA transaction.


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object for which to set or clear the channel configuration callback.


### -param ConfigureRoutine [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/405D1D3F-FC01-4223-8E28-B3FD3F0516F7">EvtDmaTransactionConfigureDmaChannel</a> event callback function, or NULL to clear it.




### -param ConfigureContext [in, optional]

A pointer to a buffer containing the context to be provided to the driver's <a href="https://msdn.microsoft.com/405D1D3F-FC01-4223-8E28-B3FD3F0516F7">EvtDmaTransactionConfigureDmaChannel</a> event callback function, or NULL.


## -returns



This method does not return a value.




## -remarks



This method allows the driver to customize the adapter configuration before programming the system DMA controller.

Typically from within an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>, a driver performs the following steps, in this order:

<ol>
<li>Calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>, or  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451182">WdfDmaTransactionInitializeUsingOffset</a>  to initialize the transaction object.</li>
<li>Calls <b>WdfDmaTransactionSetChannelConfigurationCallback</b> on the transaction object.</li>
<li>Calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>.</li>
</ol>
If the driver has specified an <a href="https://msdn.microsoft.com/405D1D3F-FC01-4223-8E28-B3FD3F0516F7">EvtDmaTransactionConfigureDmaChannel</a> event callback function by calling <b>WdfDmaTransactionSetChannelConfigurationCallback</b> and the driver subsequently calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547114">WdfDmaTransactionRelease</a>, the callback is cleared.

<b>WdfDmaTransactionSetChannelConfigurationCallback</b> must be used with a DMA enabler that specifies a system-mode DMA profile.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.




## -see-also




<a href="https://msdn.microsoft.com/405D1D3F-FC01-4223-8E28-B3FD3F0516F7">EvtDmaTransactionConfigureDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547114">WdfDmaTransactionRelease</a>
 

 

