---
UID: NF:rxprocs.RxChangeBufferingState
title: RxChangeBufferingState function (rxprocs.h)
description: RxChangeBufferingState is called to process a buffering state change request.
old-location: ifsk\rxchangebufferingstate.htm
tech.root: ifsk
ms.assetid: 83e181cd-bbec-4142-8d97-4f67285b6bb4
ms.date: 04/16/2018
ms.keywords: RxChangeBufferingState, RxChangeBufferingState function [Installable File System Drivers], ifsk.rxchangebufferingstate, rxprocs/RxChangeBufferingState, rxref_be2316b0-d89d-4f61-bd09-05d631d1cfdd.xml
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h, Struchdr.h, Fcb.h
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
-	rxprocs.h
api_name:
-	RxChangeBufferingState
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxChangeBufferingState function


## -description


<b>RxChangeBufferingState</b> is called to process a buffering state change request.


## -parameters




### -param SrvOpen

A pointer to the SRV_OPEN data structure to be changed.


### -param Context

A pointer to the context parameter for use by the network mini-redirector callback. 


### -param ComputeNewState

The value that indicates if the new buffering state is to be computed. When this value is set to <b>TRUE</b>, the new buffering state is determined by calling the network mini-redirector to compute the new buffering state. When this value is <b>FALSE</b>, the new buffering state is determined by the <i>BufferingFlags</i> member of the passed in <i>SrvOpen</i> structure.


## -returns



<b>RxChangeBufferingState</b> always returns STATUS_SUCCESS whether this routine was successful or if an error occurs. If an error occurs, the buffering state is changed so that no buffering is enabled.




## -remarks



If local buffering is disabled for this FCB (FCB_STATE_DISABLE_LOCAL_BUFFERING is set in the FcbState structure member of the FCB), this will disable local buffering independent of the open mode on the FCB and any default buffering options. When FCB_STATE_DISABLE_LOCAL_BUFFERING is set, the new buffering state set by <b>RxChangeBufferingState</b> will be to disable all buffering.

If <i>ComputeNewState</i> is <b>TRUE</b>, then the <b>MRxComputeNewBufferingState</b> routine exported by the network mini-redirector is called to compute the new buffering state to use.

If the FCB is acquired exclusively and <i>ComputeNewState</i> is <b>FALSE</b>. then <b>RxChangeBufferingState</b> will set the following buffering state options:

<ul>
<li>
FCB_STATE_WRITECACHING_ENABLED

</li>
<li>
FCB_STATE_FILESIZECACHEING_ENABLED

</li>
<li>
FCB_STATE_FILETIMECACHEING_ENABLED

</li>
<li>
FCB_STATE_WRITEBUFFERING_ENABLED

</li>
<li>
FCB_STATE_LOCK_BUFFERING_ENABLED

</li>
<li>
FCB_STATE_READBUFFERING_ENABLED

</li>
<li>
FCB_STATE_READCACHING_ENABLED

</li>
</ul>
To acquire the FCB exclusively requires that the FCB must not be opened with any of the following values:

<ul>
<li>
ShareAccess.SharedRead

</li>
<li>
ShareAccess.SharedWrite

</li>
<li>
ShareAccess.SharedDelete

</li>
</ul>
RDBSS does not currently use a number of possible buffering options, so these options are ignored internally by RDBSS when they are set off using <b>RxChangeBufferingState</b>. These ignored buffering options include the following:

<ul>
<li>
FCB_STATE_WRITEBUFFERING_ENABLED

</li>
<li>
FCB_STATE_READBUFFERING_ENABLED

</li>
<li>
FCB_STATE_OPENSHARING_ENABLED

</li>
<li>
FCB_STATE_COLLAPSING_ENABLED

</li>
<li>
FCB_STATE_FILESIZECACHEING_ENABLED

</li>
<li>
FCB_STATE_FILETIMECACHEING_ENABLED

</li>
</ul>
If the FCB_STATE_WRITECACHING_ENABLED buffering state is changed to off, any FCB in the system cache is flushed. 

On exit from <b>RxChangeBufferingState</b>, there is no change in resource ownership. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554485">RxIndicateChangeOfBufferingState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554490">RxIndicateChangeOfBufferingStateForSrvOpen</a>



<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>
 

 

