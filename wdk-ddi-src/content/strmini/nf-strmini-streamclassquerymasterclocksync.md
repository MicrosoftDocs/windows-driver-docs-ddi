---
UID: NF:strmini.StreamClassQueryMasterClockSync
title: StreamClassQueryMasterClockSync function
author: windows-driver-content
description: The minidriver may call the StreamClassQueryMasterClockSync routine to synchronously query a stream's master clock.
old-location: stream\streamclassquerymasterclocksync.htm
old-project: stream
ms.assetid: db58103d-8862-4be1-bca2-9d59d392591c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.streamclassquerymasterclocksync, StreamClassQueryMasterClockSync, StreamClassQueryMasterClockSync routine [Streaming Media Devices], strclass-routines_32944030-bbcb-4f21-98cd-09c77ad3cd53.xml, strmini/StreamClassQueryMasterClockSync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL (See Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Stream.lib
-	Stream.dll
apiname:
-	StreamClassQueryMasterClockSync
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_PRIORITY, STREAM_PRIORITY"
req.product: Windows 10 or later.
---

# StreamClassQueryMasterClockSync function


## -description


The minidriver may call the <b>StreamClassQueryMasterClockSync</b> routine to synchronously query a stream's master clock. 


## -syntax


````
VOID StreamClassQueryMasterClockSync(
  _In_    HANDLE           MasterClockHandle,
  _Inout_ PHW_TIME_CONTEXT TimeContext
);
````


## -parameters




### -param MasterClockHandle [in]

Specifies the handle for the master clock that is being queried. The class driver passes this in the SRB_INDICATE_MASTER_CLOCK request to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568467">StrMiniReceiveStreamControlPacket</a> routine.


### -param TimeContext [in, out]

Specifies the <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a> structure that the class driver passes to the master clock's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a> routine. Before calling this routine, the minidriver must fill in the <b>HwDeviceExtension</b>, <b>HwStreamObject</b>, and <b>Function</b> members of <i>TimeContext</i>. <b>StreamClassQueryMasterClockSync</b> completes the <b>Time</b> and <b>SystemTime</b> members.


## -returns


None



## -remarks


The routine must be called at or below DISPATCH_LEVEL. If the caller is running at a raised IRQL, it should use the asynchronous version, <a href="..\strmini\nf-strmini-streamclassquerymasterclock.md">StreamClassQueryMasterClock</a>, instead.

The class driver calls the master clock's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a> routine to query the clock.

On rare occasions, the graph manager switches the master clock. The class driver exposes a race condition in handling the new master clock. If the minidriver calls a stream class master clock routine immediately after it receives a new clock from the class driver, the class driver may produce unexpected results.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a>

<a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568467">StrMiniReceiveStreamControlPacket</a>

<a href="..\strmini\nf-strmini-streamclassquerymasterclock.md">StreamClassQueryMasterClock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassQueryMasterClockSync routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

