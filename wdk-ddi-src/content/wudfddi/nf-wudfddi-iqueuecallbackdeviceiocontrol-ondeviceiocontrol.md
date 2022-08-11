---
UID: NF:wudfddi.IQueueCallbackDeviceIoControl.OnDeviceIoControl
title: IQueueCallbackDeviceIoControl::OnDeviceIoControl (wudfddi.h)
description: The OnDeviceIoControl method is called to handle a device I/O control request when an application performs a specific operation on a device through the Microsoft Win32 OnDeviceIoControl function.
old-location: wdf\iqueuecallbackdeviceiocontrol_ondeviceiocontrol.htm
tech.root: wdf
ms.date: 08/11/2022
keywords: ["IQueueCallbackDeviceIoControl::OnDeviceIoControl"]
ms.keywords: IQueueCallbackDeviceIoControl interface,OnDeviceIoControl method, IQueueCallbackDeviceIoControl.OnDeviceIoControl, IQueueCallbackDeviceIoControl::OnDeviceIoControl, OnDeviceIoControl, OnDeviceIoControl method, OnDeviceIoControl method,IQueueCallbackDeviceIoControl interface, UMDFQueueObjectRef_2dd692cd-27fb-41fc-ab9d-2bb9db9b32bb.xml, umdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol, wdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol, wudfddi/IQueueCallbackDeviceIoControl::OnDeviceIoControl
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IQueueCallbackDeviceIoControl::OnDeviceIoControl
 - wudfddi/IQueueCallbackDeviceIoControl::OnDeviceIoControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IQueueCallbackDeviceIoControl::OnDeviceIoControl
---

# IQueueCallbackDeviceIoControl::OnDeviceIoControl

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **OnDeviceIoControl** method is called to handle a device I/O control request when an application performs a specific operation on a device through the Microsoft Win32 **OnDeviceIoControl** function.

## -parameters

### -param pWdfQueue [in]

A pointer to the [IWDFIoQueue](./nn-wudfddi-iwdfioqueue.md) interface for the I/O queue object that the request arrives from.

### -param pWdfRequest [in]


A pointer to the [IWDFIoRequest](./nn-wudfddi-iwdfiorequest.md) interface that represents the framework request object.

### -param ControlCode [in]


The driver-defined or system-defined I/O control code (IOCTL) that identifies the specific operation to be performed and that is associated with the request.

### -param InputBufferSizeInBytes

The size, in bytes, of the input buffer for the request.

### -param OutputBufferSizeInBytes

The size, in bytes, of the output buffer for the request.

## -remarks

A driver registers the [IQueueCallbackDeviceIoControl](./nn-wudfddi-iqueuecallbackdeviceiocontrol.md) interface when the driver calls the [IWDFDevice::CreateIoQueue](./nf-wudfddi-iwdfdevice-createioqueue.md) method to create an I/O queue or to configure the default I/O queue. 

A driver can implement a single **OnDeviceIoControl** method for all I/O queues or separate **OnDeviceIoControl** methods for each I/O queue. 

The **OnDeviceIoControl** method receives every device I/O control request type from a queue. (The request type is identified by the **WdfRequestDeviceIoControl** value of the [WDF_REQUEST_TYPE](../wdfrequest/ne-wdfrequest-_wdf_request_type.md) enumeration type for the request.) 

For more information about the driver's methods that are associated with queues and that the framework calls, see [I/O Queue Event Callback Functions](/windows-hardware/drivers/wdf/i-o-queue-event-callback-functions). The **OnDeviceIoControl** method must process each received device I/O control request. For more information about how UMDF drivers process I/O requests, see [Processing I/O Requests](/windows-hardware/drivers/wdf/processing-i-o-requests).

The driver can call the [IWDFIoRequest::GetDeviceIoControlParameters](./nf-wudfddi-iwdfiorequest-getdeviceiocontrolparameters.md), [IWDFIoRequest::GetInputMemory](./nf-wudfddi-iwdfiorequest-getinputmemory.md), and [IWDFIoRequest::GetOutputMemory](./nf-wudfddi-iwdfiorequest-getoutputmemory.md) methods to retrieve information about the request and the input and output buffers.

## -see-also

- [IQueueCallbackDeviceIoControl](./nn-wudfddi-iqueuecallbackdeviceiocontrol.md)
- [IWDFDevice::CreateIoQueue](./nf-wudfddi-iwdfdevice-createioqueue.md)
- [IWDFIoQueue](./nn-wudfddi-iwdfioqueue.md)
- [IWDFIoRequest](./nn-wudfddi-iwdfiorequest.md)
- [WDF_REQUEST_TYPE](../wdfrequest/ne-wdfrequest-_wdf_request_type.md)
