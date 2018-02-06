---
UID: NF:wdfcore.WDF_REL_TIMEOUT_IN_US
title: WDF_REL_TIMEOUT_IN_US function
author: windows-driver-content
description: The WDF_REL_TIMEOUT_IN_US function converts a specified number of microseconds to a relative time value.
old-location: wdf\wdf_rel_timeout_in_us.htm
old-project: wdf
ms.assetid: 202c9741-140e-4d6e-961b-fb92f690e743
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdf_rel_timeout_in_us, wdfcore/WDF_REL_TIMEOUT_IN_US, kmdf.wdf_rel_timeout_in_us, WDF_REL_TIMEOUT_IN_US function, DFTimerObjectRef_40b7f958-a289-43c2-ba4b-7085cc1659ee.xml, WDF_REL_TIMEOUT_IN_US
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
-	WDF_REL_TIMEOUT_IN_US
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# WDF_REL_TIMEOUT_IN_US function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REL_TIMEOUT_IN_US</b> function converts a specified number of microseconds to a relative time value.


## -syntax


````
LONGLONG WDF_REL_TIMEOUT_IN_US(
  _In_ ULONGLONG Time
);
````


## -parameters




### -param Time [in]

The number of microseconds to convert.


## -returns


<b>WDF_REL_TIMEOUT_IN_US</b> returns the relative time value, in system time units (100-nanosecond intervals), that represents the number of microseconds that <i>Time</i> specifies.



## -remarks


A relative time is a time value that is relative to the current system time. For example, if a caller passes a relative time value of five microseconds to a function that accepts a time-out value, the function will time out five microseconds after it is called.



## -see-also

<a href="..\wdfcore\nf-wdfcore-wdf_abs_timeout_in_us.md">WDF_ABS_TIMEOUT_IN_US</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REL_TIMEOUT_IN_US function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

