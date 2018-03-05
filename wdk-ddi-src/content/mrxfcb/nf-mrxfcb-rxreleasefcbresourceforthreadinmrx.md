---
UID: NF:mrxfcb.RxReleaseFcbResourceForThreadInMRx
title: RxReleaseFcbResourceForThreadInMRx function
author: windows-driver-content
description: RxReleaseFcbResourceForThreadInMRx releases the FCB resource acquired by a network mini-redirector driver with a particular thread ID.
old-location: ifsk\rxreleasefcbresourceforthreadinmrx.htm
old-project: ifsk
ms.assetid: 86b6f18b-4088-4fa3-ace3-f083f61ef0d0
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
req.lib: NtosKrnl.exe
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
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# RxReleaseFcbResourceForThreadInMRx function


## -description


<b>RxReleaseFcbResourceForThreadInMRx</b> releases the FCB resource acquired by a network mini-redirector driver with a particular thread ID. 


## -syntax


````
VOID RxReleaseFcbResourceForThreadInMRx(
  _In_    PRX_CONTEXT      pRxContext,
  _Inout_ PMRX_FCB         MrxFcb,
  _In_    ERESOURCE_THREAD ResourceThreadId
);
````


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

<a href="..\mrxfcb\nf-mrxfcb-rxacquiresharedfcbresourceinmrx.md">RxAcquireSharedFcbResourceInMRx</a>



<a href="..\mrxfcb\nf-mrxfcb-rxacquiresharedfcbresourceinmrxex.md">RxAcquireSharedFcbResourceInMRxEx</a>



<a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceinmrx.md">RxReleaseFcbResourceInMRx</a>



<a href="..\mrxfcb\nf-mrxfcb-rxacquireexclusivefcbresourceinmrx.md">RxAcquireExclusiveFcbResourceInMRx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxReleaseFcbResourceForThreadInMRx function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

