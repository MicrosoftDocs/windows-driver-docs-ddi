---
UID: NF:sercx.SerCxGetReadIntervalTimeout
title: SerCxGetReadIntervalTimeout function
author: windows-driver-content
description: The SerCxGetReadIntervalTimeout method returns the interval time-out value for a read (receive) operation.
old-location: serports\sercxgetreadintervaltimeout.htm
old-project: serports
ms.assetid: E92F181A-DBD7-44A3-A49D-DDF07E03ADB1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCxGetReadIntervalTimeout method [Serial Ports], serports.sercxgetreadintervaltimeout, 1/SerCxGetReadIntervalTimeout, SerCxGetReadIntervalTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	1.0\Sercx.h
apiname:
-	SerCxGetReadIntervalTimeout
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCxGetReadIntervalTimeout function


## -description


The <b>SerCxGetReadIntervalTimeout</b> method returns the interval time-out value for a read (receive) operation.


## -syntax


````
ULONG SerCxGetReadIntervalTimeout(
  [in] WDFDEVICE Device
);
````


## -parameters




#### - Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns


<b>SerCxGetReadIntervalTimeout</b> returns the read-interval time-out value in milliseconds. A value of zero indicates that read-interval time-outs are not used.



## -remarks


The read-interval time-out value is the maximum amount of time, in milliseconds, that is allowed between two consecutive bytes in a read operation. A read operation that exceeds this maximum times out. For more information about time-out values, see <a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>.

A read (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>) request successfully completes when the requested read operation times out. The request returns the <b>STATUS_TIMEOUT</b> status code to indicate that the operation timed out.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>

<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxGetReadIntervalTimeout method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

