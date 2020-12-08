---
UID: NF:wdfmemory.WdfMemoryGetBuffer
title: WdfMemoryGetBuffer function (wdfmemory.h)
description: The WdfMemoryGetBuffer method returns a pointer to the buffer that is associated with a specified memory object.
old-location: wdf\wdfmemorygetbuffer.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfMemoryGetBuffer function"]
ms.keywords: DFMemoryObjectRef_6f8615ee-5e34-46c5-8c83-4b52433753aa.xml, WdfMemoryGetBuffer, WdfMemoryGetBuffer method, kmdf.wdfmemorygetbuffer, wdf.wdfmemorygetbuffer, wdfmemory/WdfMemoryGetBuffer
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfMemoryGetBuffer
 - wdfmemory/WdfMemoryGetBuffer
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
 - WdfMemoryGetBuffer
---

# WdfMemoryGetBuffer function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfMemoryGetBuffer</b> method returns a pointer to the buffer that is associated with a specified memory object.

## -parameters

### -param Memory 

[in]
A handle to a framework memory object.

### -param BufferSize 

[out, optional]
A pointer to a location that receives the size, in bytes, of the memory buffer. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>WdfMemoryGetBuffer</b> returns a pointer to the memory buffer.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about framework memory objects, see <a href="/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

<b>WdfMemoryGetBuffer</b> can be called at any IRQL.


#### Examples

The following code example is based on the <a href="/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a> callback function in the <a href="/samples/browse/?redirectedfrom=MSDN-samples">kmdf_fx2</a> sample driver. The example obtains the buffer that is associated with the memory object that the callback function receives. The example copies data from the buffer into device object context space that the driver has defined.

```cpp
VOID
OsrFxEvtUsbInterruptPipeReadComplete(
    WDFUSBPIPE  Pipe,
    WDFMEMORY  Buffer,
    size_t  NumBytesTransferred,
    WDFCONTEXT  Context
    )
{
    PUCHAR  switchState = NULL;
    WDFDEVICE  device;
    PDEVICE_CONTEXT  pDeviceContext = Context;

    device = WdfObjectContextGetObject(pDeviceContext);
    switchState = WdfMemoryGetBuffer(Buffer, NULL);
    pDeviceContext->CurrentSwitchState = *switchState;
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectcontextgetobject">WdfObjectContextGetObject</a>
