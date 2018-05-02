---
UID: NS:wdfrequest._WDF_REQUEST_SEND_OPTIONS
title: "_WDF_REQUEST_SEND_OPTIONS"
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS structure specifies options that are associated with sending an I/O request to an I/O target.
old-location: wdf\wdf_request_send_options.htm
old-project: wdf
ms.assetid: 0d561e0f-ca7e-44ed-9025-1a6513e4cd28
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_REQUEST_SEND_OPTIONS, DFRequestObjectRef_3fc871af-dae6-454f-8ff8-35a8b0c5ae9a.xml, PWDF_REQUEST_SEND_OPTIONS, PWDF_REQUEST_SEND_OPTIONS structure pointer, WDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS structure, _WDF_REQUEST_SEND_OPTIONS, kmdf.wdf_request_send_options, wdf.wdf_request_send_options, wdfrequest/PWDF_REQUEST_SEND_OPTIONS, wdfrequest/WDF_REQUEST_SEND_OPTIONS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfrequest.h
api_name:
-	WDF_REQUEST_SEND_OPTIONS
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
---

# _WDF_REQUEST_SEND_OPTIONS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_SEND_OPTIONS</b> structure specifies options that are associated with sending an I/O request to an I/O target.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Flags

A bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552493">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>-typed flags.


### -field Timeout

A time-out value, in system time units (100-nanosecond intervals). If the driver has set the WDF_REQUEST_SEND_OPTION_TIMEOUT flag, the framework cancels the associated I/O request if it is not completed within the specified time-out period. The time-out value can be negative, positive, or zero, as follows:

<ul>
<li>
If the value is negative, the expiration time is relative to the current system time.

</li>
<li>
If the value is positive, the expiration time is specified as an absolute time (which is actually relative to January 1, 1601). 

</li>
<li>
If the value is zero, the framework does not time out the request.

</li>
</ul>
Relative expiration times are not affected by any changes to the system time that might occur within the specified time-out period. Absolute expiration times do reflect system time changes.

The framework provides <a href="https://msdn.microsoft.com/E7D5564D-7BAA-412E-959F-3655B963B4C1">time conversion functions</a> that convert time values into system time units.

If the framework cancels an I/O request because the specified time-out period has elapsed, the framework provides a completion status of STATUS_IO_TIMEOUT for the I/O request. However, after the time-out period elapses, the I/O target might complete the I/O request before the framework is able to cancel it. In that case, the I/O request's completion status will not be STATUS_IO_TIMEOUT.




## -remarks



The <b>WDF_REQUEST_SEND_OPTIONS</b> structure is passed to object methods that send an I/O request to an I/O target, such as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> method. The structure must be initialized by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552497">WDF_REQUEST_SEND_OPTIONS_INIT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff552498">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a> functions.

If the driver is sending the request synchronously, we recommend that the driver set a time-out value and the time-out flag in the <b>Flags</b> member of this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552493">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552497">WDF_REQUEST_SEND_OPTIONS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552498">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>
 

 

