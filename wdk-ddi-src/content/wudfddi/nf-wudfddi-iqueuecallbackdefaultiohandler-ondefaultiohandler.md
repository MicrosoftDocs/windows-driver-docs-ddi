---
UID: NF:wudfddi.IQueueCallbackDefaultIoHandler.OnDefaultIoHandler
title: IQueueCallbackDefaultIoHandler::OnDefaultIoHandler (wudfddi.h)
description: The OnDefaultIoHandler method handles I/O requests that no other method is registered to handle.
old-location: wdf\iqueuecallbackdefaultiohandler_ondefaultiohandler.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IQueueCallbackDefaultIoHandler::OnDefaultIoHandler"]
ms.keywords: IQueueCallbackDefaultIoHandler interface,OnDefaultIoHandler method, IQueueCallbackDefaultIoHandler.OnDefaultIoHandler, IQueueCallbackDefaultIoHandler::OnDefaultIoHandler, OnDefaultIoHandler, OnDefaultIoHandler method, OnDefaultIoHandler method,IQueueCallbackDefaultIoHandler interface, UMDFQueueObjectRef_21f994ea-feca-4c50-aa83-401581713c3f.xml, umdf.iqueuecallbackdefaultiohandler_ondefaultiohandler, wdf.iqueuecallbackdefaultiohandler_ondefaultiohandler, wudfddi/IQueueCallbackDefaultIoHandler::OnDefaultIoHandler
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
 - IQueueCallbackDefaultIoHandler::OnDefaultIoHandler
 - wudfddi/IQueueCallbackDefaultIoHandler::OnDefaultIoHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IQueueCallbackDefaultIoHandler::OnDefaultIoHandler
---

# IQueueCallbackDefaultIoHandler::OnDefaultIoHandler


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDefaultIoHandler</b> method handles I/O requests that no other method is registered to handle.

## -parameters

### -param pWdfQueue 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue object that the default I/O request arrives from.

### -param pWdfRequest 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface that represents the framework request object.

## -remarks

A driver registers the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackdefaultiohandler">IQueueCallbackDefaultIoHandler</a> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackdefaultiohandler">IQueueCallbackDefaultIoHandler</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>

