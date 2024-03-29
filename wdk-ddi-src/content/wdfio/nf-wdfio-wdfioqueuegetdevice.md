---
UID: NF:wdfio.WdfIoQueueGetDevice
title: WdfIoQueueGetDevice function (wdfio.h)
description: The WdfIoQueueGetDevice method returns a handle to the framework device object that a specified I/O queue belongs to.
old-location: wdf\wdfioqueuegetdevice.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfIoQueueGetDevice function"]
ms.keywords: DFQueueObjectRef_4f5c8dbb-feb5-4c08-a2ea-06d375d5a6be.xml, WdfIoQueueGetDevice, WdfIoQueueGetDevice method, kmdf.wdfioqueuegetdevice, wdf.wdfioqueuegetdevice, wdfio/WdfIoQueueGetDevice
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoQueueGetDevice
 - wdfio/WdfIoQueueGetDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfIoQueueGetDevice
---

# WdfIoQueueGetDevice function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueGetDevice</b> method returns a handle to the framework device object that a specified I/O queue belongs to.

## -parameters

### -param Queue [in]


A handle to a framework queue object.

## -returns

<b>WdfIoQueueGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about the <b>WdfIoQueueGetDevice</b> method, see <a href="/windows-hardware/drivers/wdf/managing-i-o-queues">Obtaining I/O Queue Properties</a>.


#### Examples

The following code example obtains a handle to the framework device object that is associated with the I/O queue that contains a specified request.

```cpp
WDFDEVICE  device;

device = WdfIoQueueGetDevice(WdfRequestGetIoQueue(Request));
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetioqueue">WdfRequestGetIoQueue</a>
