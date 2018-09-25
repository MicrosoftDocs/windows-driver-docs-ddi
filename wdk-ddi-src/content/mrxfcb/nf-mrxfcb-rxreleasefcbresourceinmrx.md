---
UID: NF:mrxfcb.RxReleaseFcbResourceInMRx
title: RxReleaseFcbResourceInMRx function
author: windows-driver-content
description: RxReleaseFcbResourceInMRx releases the FCB resource acquired by a network mini-redirector driver.
old-location: ifsk\rxreleasefcbresourceinmrx.htm
tech.root: ifsk
ms.assetid: 48308dcd-e423-4c25-9fec-3a423043e988
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxReleaseFcbResourceInMRx, RxReleaseFcbResourceInMRx function [Installable File System Drivers], ifsk.rxreleasefcbresourceinmrx, mrxfcb/RxReleaseFcbResourceInMRx, rxref_b433f8ba-7bdd-4fd2-baba-346e886a23dc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrxfcb.h
req.include-header: Mrxfcb.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrxfcb.h
api_name:
-	RxReleaseFcbResourceInMRx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxReleaseFcbResourceInMRx function


## -description


<b>RxReleaseFcbResourceInMRx</b> releases the FCB resource acquired by a network mini-redirector driver. 


## -parameters




### -param Fcb

<p>A pointer to the FCB. This parameter is required and cannot be <b>NULL</b>. </p>




## -returns



None 




## -remarks



The synchronization resources of interest to a network mini-redirector driver are primarily associated with the FCB. There is a paging I/O resource and a regular resource. The paging I/O resource is managed internally by RDBSS. The only resource accessible to a network mini-redirector driver is the regular resource. 

The <b>RxReleaseFcbResourceInMRx</b> routine will release an FCB resource previously acquired by calling <b>RxAcquireExclusiveFcbResourceInMRx</b>, <b>RxAcquireSharedFcbResourceInMRx</b>, or <b>RxAcquireSharedFcbResourceInMRxEx</b>. If there are any pending buffering state change requests for this FCB, then these buffering state changes will be processed first before the <b>RxReleaseFcbResourceInMRx</b> routine returns. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553363">RxAcquireExclusiveFcbResourceInMRx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553372">RxAcquireSharedFcbResourceInMRx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553375">RxAcquireSharedFcbResourceInMRxEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554694">RxReleaseFcbResourceForThreadInMRx</a>
 

 

