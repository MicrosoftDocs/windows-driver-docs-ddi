---
UID: NF:wudfddi.IWDFIoRequest.GetOutputMemory
title: IWDFIoRequest::GetOutputMemory method
author: windows-driver-content
description: The GetOutputMemory method retrieves the memory object that represents the output buffer for an I/O request.
old-location: wdf\iwdfiorequest_getoutputmemory.htm
old-project: wdf
ms.assetid: 12862fb2-4cdb-4446-aa20-ec911c9cd65f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: GetOutputMemory, GetOutputMemory method, IWDFIoRequest interface, UMDFRequestObjectRef_618a405c-a272-4427-809b-46b7f46b75de.xml, umdf.iwdfiorequest_getoutputmemory, IWDFIoRequest, wudfddi/IWDFIoRequest::GetOutputMemory, IWDFIoRequest interface, GetOutputMemory method, wdf.iwdfiorequest_getoutputmemory, IWDFIoRequest::GetOutputMemory, GetOutputMemory method
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
-	IWDFIoRequest.GetOutputMemory
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::GetOutputMemory method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetOutputMemory</b> method retrieves the memory object that represents the output buffer for an I/O request.


## -syntax


````
void GetOutputMemory(
  [out] IWDFMemory **ppWdfMemory
);
````


## -parameters




### -param ppWdfMemory [out]

A pointer to a variable that receives a pointer to the reference-counted <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for the memory object. Note that returning <b>NULL</b> is valid; in this situation, no output memory is associated with the I/O request.


## -returns


None



## -remarks


Drivers that use the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> access method can call <b>GetOutputMemory</b> to obtain an I/O request's output buffer.

Before a driver completes an I/O request, the driver must call the <b>IWDFMemory::Release</b> method for the memory object. The underlying memory object is freed when the request is completed.

The output buffer that is associated with the I/O request contains information (for example, data from a disk) that the driver provides to the originator of the request. The driver can call <b>GetOutputMemory</b> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data). To access the output buffer, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a> method.

UMDF creates an I/O request's memory objects when it receives the I/O request, before it adds the I/O request to a driver's I/O queue. If UMDF cannot allocate memory for the memory objects, it completes the I/O request with a failure return status and does not deliver the I/O request to the driver.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetOutputMemory method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

