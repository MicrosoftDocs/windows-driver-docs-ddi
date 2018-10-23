---
UID: NE:wudfddi_types._WDF_REQUEST_TYPE
title: "_WDF_REQUEST_TYPE"
author: windows-driver-content
description: The WDF_REQUEST_TYPE enumeration identifies the types of I/O requests that a UMDF request object can represent.
old-location: wdf\wdf_request_type__umdf_.htm
tech.root: wdf
ms.assetid: a883f22e-0d6f-4755-882b-ad5a60a09271
ms.date: 02/26/2018
ms.keywords: "*PWDF_REQUEST_TYPE, WDF_REQUEST_TYPE, WDF_REQUEST_TYPE enumeration, WdfRequestCleanup, WdfRequestClose, WdfRequestCreate, WdfRequestDeviceIoControl, WdfRequestFlushBuffers, WdfRequestInternalIoctl, WdfRequestMaximum, WdfRequestOther, WdfRequestQueryInformation, WdfRequestRead, WdfRequestSetInformation, WdfRequestTypeNoFormat, WdfRequestUndefined, WdfRequestUsb, WdfRequestWrite, _WDF_REQUEST_TYPE, umdf.wdf_request_type__umdf_, umdfstructs_6faf9392-ee30-4144-a96c-7f1fcc329de8.xml, wdf.wdf_request_type__umdf_, wudfddi_types/WDF_REQUEST_TYPE, wudfddi_types/WdfRequestCleanup, wudfddi_types/WdfRequestClose, wudfddi_types/WdfRequestCreate, wudfddi_types/WdfRequestDeviceIoControl, wudfddi_types/WdfRequestFlushBuffers, wudfddi_types/WdfRequestInternalIoctl, wudfddi_types/WdfRequestMaximum, wudfddi_types/WdfRequestOther, wudfddi_types/WdfRequestQueryInformation, wudfddi_types/WdfRequestRead, wudfddi_types/WdfRequestSetInformation, wudfddi_types/WdfRequestTypeNoFormat, wudfddi_types/WdfRequestUndefined, wudfddi_types/WdfRequestUsb, wudfddi_types/WdfRequestWrite"
ms.topic: enum
req.header: wudfddi_types.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_types.h
api_name:
-	WDF_REQUEST_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE, *PWDF_REQUEST_TYPE
---

# _WDF_REQUEST_TYPE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>WDF_REQUEST_TYPE</b> enumeration identifies the types of I/O requests that a UMDF request object can represent.


## -enum-fields




### -field WdfRequestUndefined

The type of the request object is undefined.


### -field WdfRequestCreate

The request object represents a file creation request. The driver receives this type of request object when an application opens a device by calling the Microsoft Win32 <b>CreateFile</b> function. The framework delivers this type of request, along with a newly created file object (<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>), to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> callback function. The new file object represents the HANDLE-typed file handle that the Win32 <b>CreateFile</b> returns. 


### -field WdfRequestCleanup

 The request object represents a file cleanup request. The driver receives this type of request object after an application's call to the Win32 <b>CloseHandle</b> function closes the last handle to a file object, but possibly before all of the file's outstanding I/O requests have been completed or canceled. The framework delivers this type of request to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554905">IFileCallbackCleanup::OnCleanupFile</a> callback function. (Also see <b>WdfRequestClose</b>.)


### -field WdfRequestRead

The request object represents a read request. This driver receives this type of I/O request when an application calls the Win32 <b>ReadFile</b> or <b>ReadFileEx</b> function. The framework delivers this type of request to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556875">IQueueCallbackRead::OnRead</a> callback function.


### -field WdfRequestWrite

The request object represents a write request. This driver receives this type of I/O request when an application calls the Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. The framework delivers this type of request to  the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556885">IQueueCallbackWrite::OnWrite</a> callback function.


### -field WdfRequestDeviceIoControl

The request object represents a device I/O control request. This driver receives this type of I/O request when an application calls the Win32 <b>DeviceIoControl</b> function. The framework delivers this type of request to  the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556854">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a> callback function.


### -field WdfRequestClose

The request object represents a file close request.  The driver receives this type of request object after an application's call to the Win32 <b>CloseHandle</b> function closes the last handle to a file object, and after all of the file's outstanding I/O requests have been completed or canceled.  The framework delivers this type of request to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554910">IFileCallbackClose::OnCloseFile</a> callback function. (Also see <b>WdfRequestCleanup</b>.)


### -field WdfRequestUsb

The request object was sent to a USB port. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560296">IWDFRequestCompletionParams::GetCompletedRequestType</a> method can return this value. 


### -field WdfRequestOther

This value is reserved for internal use only.


### -field WdfRequestInternalIoctl

This value is reserved for internal use only.


### -field WdfRequestTypeNoFormat

The request object's type has not been specified.


### -field WdfRequestFlushBuffers

The request object represents a request to flush cached buffers. The framework delivers this type of request to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. 


### -field WdfRequestQueryInformation

The request object represents a request to obtain information about a file. The framework delivers this type of request to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. 


### -field WdfRequestSetInformation

The request object represents a request to set information about a file. The framework delivers this type of request to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. 


### -field WdfRequestMaximum

The maximum value for the enumeration is exceeded.


## -remarks



The <b>WDF_REQUEST_TYPE</b> enumeration is used as an input parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff557014">IWDFDevice::ConfigureRequestDispatching</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff558946">IWDFIoQueue::ConfigureRequestDispatching</a>. It is also used for the return value of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559124">IWDFIoRequest::GetType</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560296">IWDFRequestCompletionParams::GetCompletedRequestType</a>.

For the KMDF version of this enumeration, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554905">IFileCallbackCleanup::OnCleanupFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554910">IFileCallbackClose::OnCloseFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556854">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556875">IQueueCallbackRead::OnRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556885">IQueueCallbackWrite::OnWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>
 

 

