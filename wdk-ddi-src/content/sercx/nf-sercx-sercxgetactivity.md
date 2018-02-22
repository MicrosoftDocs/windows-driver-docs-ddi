---
UID: NF:sercx.SerCxGetActivity
title: SerCxGetActivity function
author: windows-driver-content
description: The SerCxGetActivity method retrieves the status of pending work for the serial controller driver.
old-location: serports\sercxgetactivity.htm
old-project: serports
ms.assetid: 804D53F2-0F92-4262-A4C8-D171A5E69BFC
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SerCxGetActivity method [Serial Ports], SerCxGetActivity, serports.sercxgetactivity, 1/SerCxGetActivity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
-	SerCxGetActivity
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCxGetActivity function


## -description


The <b>SerCxGetActivity</b> method retrieves the status of pending work for the serial controller driver.


## -syntax


````
VOID SerCxGetActivity(
  [in]      WDFDEVICE       Device,
  [in, out] PSERCX_ACTIVITY Activity
);
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Activity [in, out]

A pointer to a caller-allocated <a href="..\sercx\ns-sercx-_sercx_activity.md">SERCX_ACTIVITY</a> structure. The caller must have previously called the <a href="..\sercx\nf-sercx-sercx_activity_init.md">SERCX_ACTIVITY_INIT</a> function to initialize this structure before its initial use. Thereafter, each <b>SerCxGetActivity</b> call updates the contents of this structure to track the work items that are ready to be processed by the controller driver.


## -returns



None.




## -remarks



The serial controller driver calls this method to receive a summary of processing work that it needs to perform on behalf of the serial framework extension (SerCx). Typically, <b>SerCxGetActivity</b> is called by the transmit/receive DPC routine in the controller driver.

The <i>Activity</i> parameter points to a <b>SERCX_ACTIVITY</b> structure that describes pending work for the controller driver. The pending work that SerCx assigns to the controller driver is driven by I/O requests from clients, but an I/O request does not necessarily spawn a work item. For example, if SerCx has a sufficient amount of received data in its memory buffer to complete a pending read request, this request does not cause the <b>Receiving</b> member of the <b>SERCX_ACTIVITY</b> structure to be set to TRUE.

To cycle through pending work items, the transmit/receive DPC routine calls <b>SerCxGetActivity</b>, processes a complete transmit or receive operation, and then calls <b>SerCxGetActivity</b> again to determine whether another operation of a different type requires work. If another operation requires work, this work might begin during the same callback but must stop if the return value from a call to <b>SerCxProgressReceive</b> or <b>SerCxProgressTransmit</b> directs the DPC routine to reschedule itself to run at a later time.

A lock protects the <b>SERCX_ACTIVITY</b> structure that is updated by the <b>SerCxGetActivity</b> call. During the call, this lock is acquired by event handlers in SerCx to update the summary of work that is currently pending for the controller driver.




## -see-also

<a href="..\sercx\nf-sercx-sercx_activity_init.md">SERCX_ACTIVITY_INIT</a>



<a href="..\sercx\nf-sercx-sercxcompletewait.md">SerCxCompleteWait</a>



<a href="..\sercx\ns-sercx-_sercx_activity.md">SERCX_ACTIVITY</a>



<a href="..\sercx\nf-sercx-sercxprogressreceive.md">SerCxProgressReceive</a>



<a href="..\sercx\nf-sercx-sercxprogresstransmit.md">SerCxProgressTransmit</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxGetActivity method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

