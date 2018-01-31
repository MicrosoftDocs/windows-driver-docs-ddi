---
UID: NC:wdfdmatransaction.EVT_WDF_RESERVE_DMA
title: EVT_WDF_RESERVE_DMA
author: windows-driver-content
description: The EvtReserveDma event callback function is called when the framework has reserved resources to execute and release a transaction. Reserved resources include map registers and the WDM DMA adapter's lock.
old-location: wdf\evtreservedma.htm
old-project: wdf
ms.assetid: 3663EF19-5F16-43D1-BFBC-28280E28D4DE
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtreservedma, EvtReserveDma callback function, EvtReserveDma, EVT_WDF_RESERVE_DMA, EVT_WDF_RESERVE_DMA, wdfdmatransaction/EvtReserveDma, kmdf.evtreservedma
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfDmaTransaction.h
apiname:
-	EvtReserveDma
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# EVT_WDF_RESERVE_DMA callback


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <i>EvtReserveDma</i> event callback function is called when the framework has reserved resources to execute and release a transaction. Reserved resources include map registers and the WDM DMA adapter's lock.


## -prototype


````
EVT_WDF_RESERVE_DMA EvtReserveDma;

VOID EvtReserveDma(
  _In_ WDFDMATRANSACTION DmaTransaction,
  _In_ PVOID             Context
)
{ ... }
````


## -parameters




#### - DmaTransaction [in]

A handle to the DMA transaction object that represents the transaction to which DMA resources were assigned.


#### - Context [in]

The context pointer that the driver specified in a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a>.


## -returns


This callback function does not return a value.



## -remarks


Drivers register an <i>EvtReserveDma</i> event callback function by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a>.

The framework calls a driver's <i>EvtReserveDma</i> event callback function when DMA resources have been assigned for exclusive use with the associated transaction object. The driver can initialize and execute the transaction multiple times while holding this reservation.

A driver typically initializes and then initiates the transaction from within its <i>EvtReserveDma</i> event callback function. For more information about the reservation sequence, see <a href="https://msdn.microsoft.com/8C5FF779-8D54-47D9-8EC6-7D4921F8F697">Reserving DMA Resources</a>.

  

The driver may call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionfreeresources.md">WdfDmaTransactionFreeResources</a> from within <i>EvtReserveDma</i>.


On operating systems earlier than Windows 8, <i>EvtReserveDma</i> must be used with an enabler that specifies a packet-mode DMA enabler.  Starting with  Windows 8, <i>EvtReserveDma</i> can also be used with an enabler that specifies a system-mode DMA enabler.



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionfreeresources.md">WdfDmaTransactionFreeResources</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_RESERVE_DMA callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

