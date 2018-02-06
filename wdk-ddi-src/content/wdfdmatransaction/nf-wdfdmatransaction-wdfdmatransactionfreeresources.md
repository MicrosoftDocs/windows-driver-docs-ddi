---
UID: NF:wdfdmatransaction.WdfDmaTransactionFreeResources
title: WdfDmaTransactionFreeResources function
author: windows-driver-content
description: The WdfDmaTransactionFreeResources method releases DMA resources that the driver previously allocated by calling WdfDmaTransactionAllocateResources.
old-location: wdf\wdfdmatransactionfreeresources.htm
old-project: wdf
ms.assetid: F35F80E7-E1B6-4219-96AF-687E0014CCB3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDmaTransactionFreeResources, PFN_WDFDMATRANSACTIONFREERESOURCES, wdfdmatransaction/WdfDmaTransactionFreeResources, wdf.wdfdmatransactionfreeresources, WdfDmaTransactionFreeResources method, kmdf.wdfdmatransactionfreeresources
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaTransactionFreeResources
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionFreeResources function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionFreeResources</b> method releases DMA resources that the driver previously allocated by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a>.


## -syntax


````
void WdfDmaTransactionFreeResources(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to the DMA transaction object that the driver provided in a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a>.


## -returns


This method does not return a value.



## -remarks


<b>WdfDmaTransactionFreeResources</b> must be used with a DMA enabler that specifies a packet or system profile.

On operating systems earlier than Windows 8, <b>WdfDmaTransactionFreeResources</b> must be used with an enabler that specifies a single-packet DMA enabler.  Starting with  Windows 8, <b>WdfDmaTransactionFreeResources</b> can also be used with an enabler that specifies a system-mode DMA enabler.

  When called with a scatter/gather DMA enabler, <b>WdfDmaTransactionFreeResources</b> causes a verifier bug check.



The driver's call to <b>WdfDmaTransactionFreeResources</b> may cause the framework to call <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> or <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_reserve_dma.md">EvtReserveDma</a> immediately.

For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.




## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionFreeResources method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

