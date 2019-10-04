---
UID: NF:wdfrequest.WdfRequestIsReserved
title: WdfRequestIsReserved function (wdfrequest.h)
description: The WdfRequestIsReserved method determines whether a specified request object is one that the framework reserved to support guaranteed forward progress during low-memory situations.
old-location: wdf\wdfrequestisreserved.htm
tech.root: wdf
ms.assetid: 8cbf75c4-d54c-45e0-9abb-bef8e76fb9fe
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_286c4c9a-cbec-48f1-9d78-516cbaab2d45.xml, WdfRequestIsReserved, WdfRequestIsReserved method, kmdf.wdfrequestisreserved, wdf.wdfrequestisreserved, wdfrequest/WdfRequestIsReserved
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestIsReserved"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfRequestIsReserved
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestIsReserved function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestIsReserved</b> method determines whether a specified request object is one that the framework reserved to support <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guaranteed forward progress</a> during low-memory situations.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestIsReserved</b> returns <b>TRUE</b> if the specified request object is one that the framework pre-allocated for low-memory situations. Otherwise the method returns <b>FALSE</b>.




## -remarks



For more information about the <b>WdfRequestIsReserved</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.


#### Examples

The following code example determines whether a request object that a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a> callback function has received is one that the driver created for low-memory situations.

```cpp
VOID
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

  ...}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>
 

 

