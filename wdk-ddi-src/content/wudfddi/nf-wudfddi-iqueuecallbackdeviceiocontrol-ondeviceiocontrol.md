---
UID: NF:wudfddi.IQueueCallbackDeviceIoControl.OnDeviceIoControl
title: IQueueCallbackDeviceIoControl::OnDeviceIoControl (wudfddi.h)
description: The OnDeviceIoControl method is called to handle a device I/O control request when an application performs a specific operation on a device through the Microsoft Win32 OnDeviceIoControl function.
old-location: wdf\iqueuecallbackdeviceiocontrol_ondeviceiocontrol.htm
tech.root: wdf
ms.assetid: ed0eac1a-8e41-44c3-a538-9ec48492425f
ms.date: 02/26/2018
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
 - IQueueCallbackDeviceIoControl.OnDeviceIoControl
---

# IQueueCallbackDeviceIoControl::OnDeviceIoControl


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDeviceIoControl</b> method is called to handle a device I/O control request when an application performs a specific operation on a device through the Microsoft Win32 <b>OnDeviceIoControl</b> function.

## -parameters

### -param pWdfQueue 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from.

### -param pWdfRequest 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface that represents the framework request object.

### -param ControlCode 

[in]
The driver-defined or system-defined I/O control code (IOCTL) that identifies the specific operation to be performed and that is associated with the request.

### -param InputBufferSizeInBytes

### -param OutputBufferSizeInBytes

#### - InBufferSize [in]

The size, in bytes, of the input buffer for the request.


#### - OutBufferSize [in]

The size, in bytes, of the output buffer for the request.

## -remarks

A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackdeviceiocontrol">IQueueCallbackDeviceIoControl</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 

A driver can implement a single <b>OnDeviceIoControl</b> method for all I/O queues or separate <b>OnDeviceIoControl</b> methods for each I/O queue. 

The <b>OnDeviceIoControl</b> method receives every device I/O control request type from a queue. (The request type is identified by the <b>WdfRequestDeviceIoControl</b> value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a> enumeration type for the request.) 

For more information about the driver's methods that are associated with queues and that the framework calls, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/i-o-queue-event-callback-functions">I/O Queue Event Callback Functions</a>. The <b>OnDeviceIoControl</b> method must process each received device I/O control request. For more information about how UMDF drivers process I/O requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

The driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getdeviceiocontrolparameters">IWDFIoRequest::GetDeviceIoControlParameters</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFIoRequest::GetInputMemory</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a> methods to retrieve information about the request and the input and output buffers.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackdeviceiocontrol">IQueueCallbackDeviceIoControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>

