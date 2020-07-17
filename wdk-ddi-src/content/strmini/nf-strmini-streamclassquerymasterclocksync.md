---
UID: NF:strmini.StreamClassQueryMasterClockSync
title: StreamClassQueryMasterClockSync function (strmini.h)
description: The minidriver may call the StreamClassQueryMasterClockSync routine to synchronously query a stream's master clock.
old-location: stream\streamclassquerymasterclocksync.htm
tech.root: stream
ms.assetid: db58103d-8862-4be1-bca2-9d59d392591c
ms.date: 04/23/2018
keywords: ["StreamClassQueryMasterClockSync function"]
ms.keywords: StreamClassQueryMasterClockSync, StreamClassQueryMasterClockSync routine [Streaming Media Devices], strclass-routines_32944030-bbcb-4f21-98cd-09c77ad3cd53.xml, stream.streamclassquerymasterclocksync, strmini/StreamClassQueryMasterClockSync
f1_keywords:
 - "strmini/StreamClassQueryMasterClockSync"
 - "StreamClassQueryMasterClockSync"
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
req.irql: <=DISPATCH_LEVEL (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassQueryMasterClockSync
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassQueryMasterClockSync function


## -description


The minidriver may call the <b>StreamClassQueryMasterClockSync</b> routine to synchronously query a stream's master clock. 


## -parameters




### -param MasterClockHandle [in]

Specifies the handle for the master clock that is being queried. The class driver passes this in the SRB_INDICATE_MASTER_CLOCK request to the minidriver's <a href="https://docs.microsoft.com/previous-versions/ff568467(v=vs.85)">StrMiniReceiveStreamControlPacket</a> routine.


### -param TimeContext [in, out]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a> structure that the class driver passes to the master clock's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a> routine. Before calling this routine, the minidriver must fill in the <b>HwDeviceExtension</b>, <b>HwStreamObject</b>, and <b>Function</b> members of <i>TimeContext</i>. <b>StreamClassQueryMasterClockSync</b> completes the <b>Time</b> and <b>SystemTime</b> members.


## -returns



None




## -remarks



The routine must be called at or below DISPATCH_LEVEL. If the caller is running at a raised IRQL, it should use the asynchronous version, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclock">StreamClassQueryMasterClock</a>, instead.

The class driver calls the master clock's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a> routine to query the clock.

On rare occasions, the graph manager switches the master clock. The class driver exposes a race condition in handling the new master clock. If the minidriver calls a stream class master clock routine immediately after it receives a new clock from the class driver, the class driver may produce unexpected results.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a>



<a href="https://docs.microsoft.com/previous-versions/ff568467(v=vs.85)">StrMiniReceiveStreamControlPacket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclock">StreamClassQueryMasterClock</a>
 

 

