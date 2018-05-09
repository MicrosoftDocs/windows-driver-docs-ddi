---
UID: NF:wdfdmatransaction.WdfDmaTransactionFreeResources
title: WdfDmaTransactionFreeResources function
author: windows-driver-content
description: The WdfDmaTransactionFreeResources method releases DMA resources that the driver previously allocated by calling WdfDmaTransactionAllocateResources.
old-location: wdf\wdfdmatransactionfreeresources.htm
old-project: wdf
ms.assetid: F35F80E7-E1B6-4219-96AF-687E0014CCB3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDmaTransactionFreeResources, WdfDmaTransactionFreeResources method, kmdf.wdfdmatransactionfreeresources, wdf.wdfdmatransactionfreeresources, wdfdmatransaction/WdfDmaTransactionFreeResources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
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
-	WdfDmaTransactionFreeResources
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionFreeResources function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionFreeResources</b> method releases DMA resources that the driver previously allocated by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>.


## -parameters




### -param DmaTransaction [in]

A handle to the DMA transaction object that the driver provided in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>.


## -returns



This method does not return a value.




## -remarks



<b>WdfDmaTransactionFreeResources</b> must be used with a DMA enabler that specifies a packet or system profile.

On operating systems earlier than Windows 8, <b>WdfDmaTransactionFreeResources</b> must be used with an enabler that specifies a single-packet DMA enabler.  Starting with  Windows 8, <b>WdfDmaTransactionFreeResources</b> can also be used with an enabler that specifies a system-mode DMA enabler.

  When called with a scatter/gather DMA enabler, <b>WdfDmaTransactionFreeResources</b> causes a verifier bug check.



The driver's call to <b>WdfDmaTransactionFreeResources</b> may cause the framework to call <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> or <a href="https://msdn.microsoft.com/3663EF19-5F16-43D1-BFBC-28280E28D4DE">EvtReserveDma</a> immediately.

For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>
 

 

