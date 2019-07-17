---
UID: NF:sercx.SerCxGetReadIntervalTimeout
title: SerCxGetReadIntervalTimeout function (sercx.h)
description: The SerCxGetReadIntervalTimeout method returns the interval time-out value for a read (receive) operation.
old-location: serports\sercxgetreadintervaltimeout.htm
tech.root: serports
ms.assetid: E92F181A-DBD7-44A3-A49D-DDF07E03ADB1
ms.date: 04/23/2018
ms.keywords: 1/SerCxGetReadIntervalTimeout, SerCxGetReadIntervalTimeout, SerCxGetReadIntervalTimeout method [Serial Ports], serports.sercxgetreadintervaltimeout
ms.topic: function
f1_keywords:
 - "sercx/SerCxGetReadIntervalTimeout"
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 1.0\Sercx.h
api_name:
- SerCxGetReadIntervalTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCxGetReadIntervalTimeout function


## -description


The <b>SerCxGetReadIntervalTimeout</b> method returns the interval time-out value for a read (receive) operation.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns



<b>SerCxGetReadIntervalTimeout</b> returns the read-interval time-out value in milliseconds. A value of zero indicates that read-interval time-outs are not used.




## -remarks



The read-interval time-out value is the maximum amount of time, in milliseconds, that is allowed between two consecutive bytes in a read operation. A read operation that exceeds this maximum times out. For more information about time-out values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>.

A read (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>) request successfully completes when the requested read operation times out. The request returns the <b>STATUS_TIMEOUT</b> status code to indicate that the operation timed out.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>
 

 

