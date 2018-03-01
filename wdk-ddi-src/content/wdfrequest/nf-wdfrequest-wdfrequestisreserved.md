---
UID: NF:wdfrequest.WdfRequestIsReserved
title: WdfRequestIsReserved function
author: windows-driver-content
description: The WdfRequestIsReserved method determines whether a specified request object is one that the framework reserved to support guaranteed forward progress during low-memory situations.
old-location: wdf\wdfrequestisreserved.htm
old-project: wdf
ms.assetid: 8cbf75c4-d54c-45e0-9abb-bef8e76fb9fe
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFRequestObjectRef_286c4c9a-cbec-48f1-9d78-516cbaab2d45.xml, WdfRequestIsReserved, WdfRequestIsReserved method, kmdf.wdfrequestisreserved, wdf.wdfrequestisreserved, wdfrequest/WdfRequestIsReserved
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfRequestIsReserved
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestIsReserved function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestIsReserved</b> method determines whether a specified request object is one that the framework reserved to support <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guaranteed forward progress</a> during low-memory situations.


## -syntax


````
BOOLEAN WdfRequestIsReserved(
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestIsReserved</b> returns <b>TRUE</b> if the specified request object is one that the framework pre-allocated for low-memory situations. Otherwise the method returns <b>FALSE</b>.




## -remarks



For more information about the <b>WdfRequestIsReserved</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.


#### Examples

The following code example determines whether a request object that a driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a> callback function has received is one that the driver created for low-memory situations.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
  MyIoRead (
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
  {...
  if (WdfRequestIsReserved(Request)) {
  // Low memory situation exists.
  ...
  }
  else {
  // Low memory situation does not exist.
  ...
  }

  ...}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestIsReserved method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

