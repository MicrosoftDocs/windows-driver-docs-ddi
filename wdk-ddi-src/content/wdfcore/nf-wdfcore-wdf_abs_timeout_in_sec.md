---
UID: NF:wdfcore.WDF_ABS_TIMEOUT_IN_SEC
title: WDF_ABS_TIMEOUT_IN_SEC function
author: windows-driver-content
description: The WDF_ABS_TIMEOUT_IN_SEC function converts a specified number of seconds to an absolute time value.
old-location: wdf\wdf_abs_timeout_in_sec.htm
old-project: wdf
ms.assetid: 492bdc23-7e55-4e6d-9d7c-189a94934049
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdfcore/WDF_ABS_TIMEOUT_IN_SEC, WDF_ABS_TIMEOUT_IN_SEC function, wdf.wdf_abs_timeout_in_sec, WDF_ABS_TIMEOUT_IN_SEC, DFTimerObjectRef_681839d3-3160-4f57-beeb-b5fe66dad3fe.xml, kmdf.wdf_abs_timeout_in_sec
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
-	WDF_ABS_TIMEOUT_IN_SEC
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# WDF_ABS_TIMEOUT_IN_SEC function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_ABS_TIMEOUT_IN_SEC</b> function converts a specified number of seconds to an absolute time value.


## -syntax


````
LONGLONG WDF_ABS_TIMEOUT_IN_SEC(
  _In_ ULONGLONG Time
);
````


## -parameters




### -param Time [in]

The number of seconds to convert.


## -returns



<b>WDF_ABS_TIMEOUT_IN_SEC</b> returns the absolute time value, in system time units (100-nanosecond intervals), that represents the number of seconds that <i>Time</i> specifies.




## -remarks



An absolute time value is a time value that specifies a specific date and time. Absolute times are relative to 00:00, January 1, 1601. If an absolute time value is passed to the system, the system adds the absolute time value to the time value that represents 00:00, January 1, 1601.




## -see-also

<a href="..\wdfcore\nf-wdfcore-wdf_rel_timeout_in_sec.md">WDF_REL_TIMEOUT_IN_SEC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_ABS_TIMEOUT_IN_SEC function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

