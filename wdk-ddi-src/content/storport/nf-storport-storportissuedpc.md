---
UID: NF:storport.StorPortIssueDpc
title: StorPortIssueDpc function
author: windows-driver-content
description: The StorPortIssueDpc routine issues a deferred procedure call (DPC).
old-location: storage\storportissuedpc.htm
old-project: storage
ms.assetid: a0c46c51-f6c4-4609-9dba-b730f33c3ed6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortIssueDpc, StorPortIssueDpc routine [Storage Devices], storage.storportissuedpc, storport/StorPortIssueDpc, storprt_e9cbe677-4d21-4c07-97a2-9db50858321f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
-	storport.h
api_name:
-	StorPortIssueDpc
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortIssueDpc function


## -description


The <b>StorPortIssueDpc</b> routine issues a deferred procedure call (DPC). 


## -parameters




### -param DeviceExtension [in]

Pointer to the per-adapter device extension. 


### -param Dpc [in]

Pointer to a buffer containing an initialized DPC object of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567579">STOR_DPC</a> returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567110">StorPortInitializeDpc</a> routine. 


### -param SystemArgument1 [in]

Pointer to caller-supplied information that will be passed to the deferred routine. 


### -param SystemArgument2 [in]

Pointer to caller-supplied information that will be passed to the deferred routine. 


## -returns



The <b>StorPortIssueDpc</b> routine returns <b>TRUE</b> if the DPC was successfully inserted into the DPC queue, and <b>FALSE</b> otherwise. 




## -remarks



The <b>StorPortIssueDpc</b>  routine calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a> kernel routine to queue the DPC. The <b>KeInsertQueueDpc</b> kernel routine does not allow a DPC to be queued multiple times. Thus, if the DPC object specified by the <i>Dpc</i> parameter is already in the DPC queue, <b>KeInsertQueueDpc</b> ignores the queue request. This ensures that a deferred routine initialized with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567110">StorPortInitializeDpc</a> is always synchronized with itself. In other words, the caller does not need to sequentialize calls to the <b>StorPortIssueDpc</b> routine to ensure that multiple instances the routine do not run simultaneously. 

If a miniport driver has multiple work-items that must be performed by the same DPC, the miniport driver must ensure that each work item completes before issuing the DPC for the next work item. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567579">STOR_DPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567110">StorPortInitializeDpc</a>
 

 

