---
UID: NF:fcb.RxpTrackReference
title: RxpTrackReference function
author: windows-driver-content
description: RxpTrackReference tracks requests to reference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these reference requests can be accessed by the logging system and WMI.
old-location: ifsk\rxptrackreference.htm
old-project: ifsk
ms.assetid: af697ccd-a748-45f8-97bb-fe595d81b693
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxpTrackReference, RxpTrackReference function [Installable File System Drivers], fcb/RxpTrackReference, ifsk.rxptrackreference, rxref_12b9266b-6cd9-4011-b764-b62376e0a5fb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fcb.h
api_name:
-	RxpTrackReference
product:
- Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxpTrackReference function


## -description


<b>RxpTrackReference</b> tracks requests to reference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these reference requests can be accessed by the logging system and WMI. 


## -parameters




### -param TraceType [in]

The value that determines which reference request type is tracked. This value can be one of the following macros defined in <i>fcb.h</i>:





#### RDBSS_REF_TRACK_SRVCALL

A reference request on a SRV_CALL structure.



#### RDBSS_REF_TRACK_NETROOT

A reference request on a NET_ROOT structure.



#### RDBSS_REF_TRACK_VNETROOT

A reference request on a V_NET_ROOT structure.



#### RDBSS_REF_TRACK_NETFOBX

A reference request on an FOBX structure.



#### RDBSS_REF_TRACK_NETFCB

A reference request on an FCB structure.



#### RDBSS_REF_TRACK_SRVOPEN

A reference request on a SRV_OPEN structure.


### -param FileName [in]

The name of the source file where this routine was called.


### -param Line [in]

The line number in the source file where this routine was called.


### -param Instance

TBD




#### - pInstance [in]

A pointer to the structure to be referenced.


## -returns



<b>RxpTrackReference</b> always returns <b>TRUE</b> on checked builds. 




## -remarks



In checked builds, <b>RxpTrackReference</b> is used to track requests to reference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures. For retail builds, this function does nothing.

If WMI is enabled, a log of these dereference operations is sent as a WMI event to user-mode WMI components that have requested notification. The deference request is also logged to the RDBSS logging system by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557368">_RxLog</a> routine to record an I/O error log entry if logging is enabled. 

Note that this routine does not actually reference the structure passed (increment the reference count on the structure).

A number of macros are defined in <i>fcb.h</i> for debugging that are the preferred way to call this routine. These macros provide a wrapper around the <b>RxReference</b> or <b>RxDereference</b> routines used for file structure management operations on SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures. These macros first call the corresponding <b>RxpTrackReference</b> routine to log diagnostic information about the request before calling the corresponding <b>RxReference</b> routine.

For retail builds, this function does nothing. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553384">RxAssert</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554385">RxDbgBreakPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554688">RxReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554655">RxpTrackDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557368">_RxLog</a>
 

 

