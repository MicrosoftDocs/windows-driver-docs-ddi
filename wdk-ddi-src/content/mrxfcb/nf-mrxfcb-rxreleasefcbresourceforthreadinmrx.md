---
UID: NF:mrxfcb.RxReleaseFcbResourceForThreadInMRx
title: RxReleaseFcbResourceForThreadInMRx function
author: windows-driver-content
description: RxReleaseFcbResourceForThreadInMRx releases the FCB resource acquired by a network mini-redirector driver with a particular thread ID.
old-location: ifsk\rxreleasefcbresourceforthreadinmrx.htm
tech.root: ifsk
ms.assetid: 86b6f18b-4088-4fa3-ace3-f083f61ef0d0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxReleaseFcbResourceForThreadInMRx, RxReleaseFcbResourceForThreadInMRx function [Installable File System Drivers], ifsk.rxreleasefcbresourceforthreadinmrx, mrxfcb/RxReleaseFcbResourceForThreadInMRx, rxref_bed9a8b0-1761-413e-b816-599b51a7f305.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrxfcb.h
req.include-header: Mrxfcb.h
req.target-type: Desktop
req.target-min-winverclnt: RxReleaseFcbResourceForThreadInMRx is only available on Windows Server 2003 SP1 and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrxfcb.h
api_name:
-	RxReleaseFcbResourceForThreadInMRx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxReleaseFcbResourceForThreadInMRx function


## -description


<b>RxReleaseFcbResourceForThreadInMRx</b> releases the FCB resource acquired by a network mini-redirector driver with a particular thread ID. 


## -parameters




### -param pRxContext [in]

A pointer to the RX_CONTEXT structure.


### -param MrxFcb [in, out]

A pointer to the FCB. This parameter is required and cannot be <b>NULL</b>. 


### -param ResourceThreadId [in]

The thread ID that originally acquired the resource.


## -returns



None 




## -remarks



The synchronization resources of interest to a network mini-redirector driver are primarily associated with the FCB. There is a paging I/O resource and a regular resource. The paging I/O resource is managed internally by RDBSS. The only resource accessible to a network mini-redirector driver is the regular resource. 

The <b>RxReleaseFcbResourceForThreadInMRx</b> routine will release an FCB resource previously acquired for a particular thread ID. This resource would have been acquired by calling <b>RxAcquireExclusiveFcbResourceInMRx</b>, <b>RxAcquireSharedFcbResourceInMRx</b>, or <b>RxAcquireSharedFcbResourceInMRxEx</b>. If there are any pending buffering state change requests for this FCB, then these buffering state changes will be processed first before the <b>RxReleaseFcbResourceForThreadInMRx</b> routine returns.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553363">RxAcquireExclusiveFcbResourceInMRx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553372">RxAcquireSharedFcbResourceInMRx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553375">RxAcquireSharedFcbResourceInMRxEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554699">RxReleaseFcbResourceInMRx</a>
 

 

