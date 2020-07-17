---
UID: NF:fcb.RxpTrackDereference
title: RxpTrackDereference function (fcb.h)
description: RxpTrackDereference is used in checked builds to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these dereference requests can be accessed by the logging system and WMI.
old-location: ifsk\rxptrackdereference.htm
tech.root: ifsk
ms.assetid: eaff92d2-d866-4096-8528-0672255ced60
ms.date: 04/16/2018
keywords: ["RxpTrackDereference function"]
ms.keywords: RxpTrackDereference, RxpTrackDereference function [Installable File System Drivers], fcb/RxpTrackDereference, ifsk.rxptrackdereference, rxref_60f3cce5-bd6b-47b9-a6cc-85b5ee027934.xml
f1_keywords:
 - "fcb/RxpTrackDereference"
 - "RxpTrackDereference"
req.header: fcb.h
req.include-header: Fcb.h
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fcb.h
api_name:
- RxpTrackDereference
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxpTrackDereference function


## -description


<b>RxpTrackDereference</b> is used in checked builds to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these dereference requests can be accessed by the logging system and WMI. 


## -parameters




### -param TraceType [in]

The value that determines which dereference request type is tracked. This value can be one of the following macros defined in <i>fcb.h</i>:





#### RDBSS_REF_TRACK_SRVCALL

A dereference request on a SRV_CALL structure.



#### RDBSS_REF_TRACK_NETROOT

A dereference request on a NET_ROOT structure.



#### RDBSS_REF_TRACK_VNETROOT

A dereference request on a V_NET_ROOT structure.



#### RDBSS_REF_TRACK_NETFOBX

A dereference request on an FOBX structure.



#### RDBSS_REF_TRACK_NETFCB

A dereference request on an FCB structure.



#### RDBSS_REF_TRACK_SRVOPEN

A dereference request on a SRV_OPEN structure.


### -param FileName [in]

The name of the source file where this routine was called.


### -param Line [in]

The line number in the source file where this routine was called.


### -param Instance

<p>A pointer to the structure to be dereferenced.</p>




## -returns



<b>RxpTrackDereference</b> always returns <b>TRUE</b> on checked builds. 




## -remarks



In checked builds, <b>RxpTrackDereference</b> is used to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures. For retail builds, this function does nothing.

If WMI is enabled, a log of the dereference requests is sent as a WMI event to user-mode WMI components that have requested notification. The deference request is also logged to the RDBSS logging system by calling the <b>_RxLog</b> routine to record an I/O error log entry if logging is enabled. 

Note that this routine does not actually dereference the structure passed (decrement the reference count on the structure).

A number of macros are defined in <i>fcb.h</i> for debugging that are the preferred way to call this routine. These macros provide a wrapper around the <b>RxReference</b> or <b>RxDereference</b> routines used for file structure management operations on SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures. These macros first call the corresponding <b>RxpTrackDereference</b> routine to log diagnostic information about the request before calling the corresponding <b>RxDereference</b> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/rxassert">RxAssert</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/rxdbgbreakpoint">RxDbgBreakPoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxptrackreference">RxpTrackReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxlog/nf-rxlog-_rxlog">_RxLog</a>
 

 

