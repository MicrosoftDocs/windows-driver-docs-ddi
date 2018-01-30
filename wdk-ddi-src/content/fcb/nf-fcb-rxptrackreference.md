---
UID: NF:fcb.RxpTrackReference
title: RxpTrackReference function
author: windows-driver-content
description: RxpTrackReference tracks requests to reference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these reference requests can be accessed by the logging system and WMI.
old-location: ifsk\rxptrackreference.htm
old-project: ifsk
ms.assetid: af697ccd-a748-45f8-97bb-fe595d81b693
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rxptrackreference, rxref_12b9266b-6cd9-4011-b764-b62376e0a5fb.xml, fcb/RxpTrackReference, RxpTrackReference function [Installable File System Drivers], RxpTrackReference
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fcb.h
apiname:
-	RxpTrackReference
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxpTrackReference function


## -description


<b>RxpTrackReference</b> tracks requests to reference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these reference requests can be accessed by the logging system and WMI. 


## -syntax


````
VOID RxpTrackReference(
  _In_ ULONG TraceType,
  _In_ PCSTR FileName,
  _In_ ULONG Line,
  _In_ PVOID pInstance
);
````


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

If WMI is enabled, a log of these dereference operations is sent as a WMI event to user-mode WMI components that have requested notification. The deference request is also logged to the RDBSS logging system by calling the <a href="..\rxlog\nf-rxlog-_rxlog.md">_RxLog</a> routine to record an I/O error log entry if logging is enabled. 

Note that this routine does not actually reference the structure passed (increment the reference count on the structure).

A number of macros are defined in <i>fcb.h</i> for debugging that are the preferred way to call this routine. These macros provide a wrapper around the <b>RxReference</b> or <b>RxDereference</b> routines used for file structure management operations on SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures. These macros first call the corresponding <b>RxpTrackReference</b> routine to log diagnostic information about the request before calling the corresponding <b>RxReference</b> routine.

For retail builds, this function does nothing. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554385">RxDbgBreakPoint</a>

<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>

<a href="..\fcb\nf-fcb-rxptrackdereference.md">RxpTrackDereference</a>

<a href="..\rxlog\nf-rxlog-_rxlog.md">_RxLog</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553384">RxAssert</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxpTrackReference function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

