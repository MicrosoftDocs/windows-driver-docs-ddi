---
UID: NS:wdfrequest._WDF_REQUEST_SEND_OPTIONS
title: "_WDF_REQUEST_SEND_OPTIONS"
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS structure specifies options that are associated with sending an I/O request to an I/O target.
old-location: wdf\wdf_request_send_options.htm
old-project: wdf
ms.assetid: 0d561e0f-ca7e-44ed-9025-1a6513e4cd28
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: "*PWDF_REQUEST_SEND_OPTIONS, PWDF_REQUEST_SEND_OPTIONS structure pointer, wdfrequest/PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS structure, WDF_REQUEST_SEND_OPTIONS, DFRequestObjectRef_3fc871af-dae6-454f-8ff8-35a8b0c5ae9a.xml, PWDF_REQUEST_SEND_OPTIONS, _WDF_REQUEST_SEND_OPTIONS, wdf.wdf_request_send_options, kmdf.wdf_request_send_options, wdfrequest/WDF_REQUEST_SEND_OPTIONS"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfrequest.h
apiname:
-	WDF_REQUEST_SEND_OPTIONS
product: Windows
targetos: Windows
req.typenames: "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product: Windows 10 or later.
---

# _WDF_REQUEST_SEND_OPTIONS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_SEND_OPTIONS</b> structure specifies options that are associated with sending an I/O request to an I/O target.


## -syntax


````
typedef struct _WDF_REQUEST_SEND_OPTIONS {
  ULONG    Size;
  ULONG    Flags;
  LONGLONG Timeout;
} WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Flags

A bitwise OR of <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_send_options_flags.md">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>-typed flags.


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
</ul>Relative expiration times are not affected by any changes to the system time that might occur within the specified time-out period. Absolute expiration times do reflect system time changes.

The framework provides <a href="https://msdn.microsoft.com/E7D5564D-7BAA-412E-959F-3655B963B4C1">time conversion functions</a> that convert time values into system time units.

If the framework cancels an I/O request because the specified time-out period has elapsed, the framework provides a completion status of STATUS_IO_TIMEOUT for the I/O request. However, after the time-out period elapses, the I/O target might complete the I/O request before the framework is able to cancel it. In that case, the I/O request's completion status will not be STATUS_IO_TIMEOUT.




## -remarks


The <b>WDF_REQUEST_SEND_OPTIONS</b> structure is passed to object methods that send an I/O request to an I/O target, such as the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> method. The structure must be initialized by calling the <a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_init.md">WDF_REQUEST_SEND_OPTIONS_INIT</a> and <a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_set_timeout.md">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a> functions.

If the driver is sending the request synchronously, we recommend that the driver set a time-out value and the time-out flag in the <b>Flags</b> member of this structure.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_set_timeout.md">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a>

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_send_options_flags.md">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>

<a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_init.md">WDF_REQUEST_SEND_OPTIONS_INIT</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

