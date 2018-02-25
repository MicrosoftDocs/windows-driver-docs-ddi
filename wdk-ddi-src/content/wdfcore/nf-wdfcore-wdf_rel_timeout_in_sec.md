---
UID: NF:wdfcore.WDF_REL_TIMEOUT_IN_SEC
title: WDF_REL_TIMEOUT_IN_SEC function
author: windows-driver-content
description: The WDF_REL_TIMEOUT_IN_SEC function converts a specified number of seconds to a relative time value.
old-location: wdf\wdf_rel_timeout_in_sec.htm
old-project: wdf
ms.assetid: 40d0f5bf-609e-4609-8785-261b087fa372
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, D, DFTimerObjectRef_2c5d8c96-3c4d-484d-9d60-656c4c4a7cc5.xml, E, F, I, L, M, N, O, R, S, T, U, W, WDF_REL_TIMEOUT_IN_SEC, WDF_REL_TIMEOUT_IN_SEC function, _, kmdf.wdf_rel_timeout_in_sec, wdf.wdf_rel_timeout_in_sec, wdfcore/WDF_REL_TIMEOUT_IN_SEC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcore.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.lib: None
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	None
-	None.dll
apiname:
-	WDF_REL_TIMEOUT_IN_SEC
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# WDF_REL_TIMEOUT_IN_SEC function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REL_TIMEOUT_IN_SEC</b> function converts a specified number of seconds to a relative time value.


## -syntax


````
LONGLONG WDF_REL_TIMEOUT_IN_SEC(
  _In_ ULONGLONG Time
);
````


## -parameters




### -param Time [in]

The number of seconds to convert.


## -returns



<b>WDF_REL_TIMEOUT_IN_SEC</b> returns the relative time value, in system time units (100-nanosecond intervals), that represents the number of seconds that <i>Time</i> specifies.




## -remarks



A relative time is a time value that is relative to the current system time. For example, if a caller passes a relative time value of five seconds to a function that accepts a time-out value, the function will time out five seconds after it is called.


#### Examples

The following code example specifies a relative timeout value of 5 seconds for an I/O request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_REQUEST_SEND_OPTIONS  requestSendOptions;
...
requestSendOptions.Timeout = WDF_REL_TIMEOUT_IN_SEC(5);
...</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfcore\nf-wdfcore-wdf_abs_timeout_in_sec.md">WDF_ABS_TIMEOUT_IN_SEC</a>



<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REL_TIMEOUT_IN_SEC function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

