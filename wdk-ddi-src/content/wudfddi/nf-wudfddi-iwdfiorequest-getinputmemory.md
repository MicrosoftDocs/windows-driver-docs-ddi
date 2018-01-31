---
UID: NF:wudfddi.IWDFIoRequest.GetInputMemory
title: IWDFIoRequest::GetInputMemory method
author: windows-driver-content
description: The GetInputMemory method retrieves the memory object that represents the input buffer in an I/O request.
old-location: wdf\iwdfiorequest_getinputmemory.htm
old-project: wdf
ms.assetid: be3f965b-69fe-4d5e-b1b6-3a370603cd7b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: UMDFRequestObjectRef_80c18660-b423-42b0-879d-a8732d2e7796.xml, GetInputMemory method, IWDFIoRequest interface, GetInputMemory method, IWDFIoRequest, umdf.iwdfiorequest_getinputmemory, wudfddi/IWDFIoRequest::GetInputMemory, GetInputMemory, wdf.iwdfiorequest_getinputmemory, IWDFIoRequest interface, GetInputMemory method, IWDFIoRequest::GetInputMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequest.GetInputMemory
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::GetInputMemory method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInputMemory</b> method retrieves the memory object that represents the input buffer in an I/O request.


## -syntax


````
void GetInputMemory(
  [out] IWDFMemory **ppWdfMemory
);
````


## -parameters




#### - ppWdfMemory [out]

A pointer to a variable that receives a pointer to the reference-counted <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for the memory object. Note that returning <b>NULL</b> is valid; in this situation, no input memory is associated with the I/O request.


## -returns


None



## -remarks


Drivers that use the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> access method can call <b>GetInputMemory</b> to obtain an I/O request's input buffer.

Before a driver completes an I/O request, the driver must call the <b>IWDFMemory::Release</b> method for the memory object. The underlying memory object is freed when the request is completed.

The input buffer that is associated with the I/O request contains information (for example, data to be written to a disk) that the originator of the request supplied. The driver can call <b>GetInputMemory</b> to obtain the input buffer for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data). To access the input buffer, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a> method.

UMDF creates an I/O request's memory objects when it receives the I/O request, before it adds the I/O request to a driver's I/O queue. If UMDF cannot allocate memory for the memory objects, it completes the I/O request with a failure return status and does not deliver the I/O request to the driver.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a>

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetInputMemory method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

