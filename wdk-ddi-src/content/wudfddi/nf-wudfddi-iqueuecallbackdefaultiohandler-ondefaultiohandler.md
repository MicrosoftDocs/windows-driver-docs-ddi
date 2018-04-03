---
UID: NF:wudfddi.IQueueCallbackDefaultIoHandler.OnDefaultIoHandler
title: IQueueCallbackDefaultIoHandler::OnDefaultIoHandler method
author: windows-driver-content
description: The OnDefaultIoHandler method handles I/O requests that no other method is registered to handle.
old-location: wdf\iqueuecallbackdefaultiohandler_ondefaultiohandler.htm
old-project: wdf
ms.assetid: d0973dc9-58d6-486f-860e-a891600be73e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IQueueCallbackDefaultIoHandler, IQueueCallbackDefaultIoHandler interface, OnDefaultIoHandler method, IQueueCallbackDefaultIoHandler::OnDefaultIoHandler, OnDefaultIoHandler method, OnDefaultIoHandler method, IQueueCallbackDefaultIoHandler interface, OnDefaultIoHandler,IQueueCallbackDefaultIoHandler.OnDefaultIoHandler, UMDFQueueObjectRef_21f994ea-feca-4c50-aa83-401581713c3f.xml, umdf.iqueuecallbackdefaultiohandler_ondefaultiohandler, wdf.iqueuecallbackdefaultiohandler_ondefaultiohandler, wudfddi/IQueueCallbackDefaultIoHandler::OnDefaultIoHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IQueueCallbackDefaultIoHandler.OnDefaultIoHandler
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IQueueCallbackDefaultIoHandler::OnDefaultIoHandler method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDefaultIoHandler</b> method handles I/O requests that no other method is registered to handle. 


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a> interface for the I/O queue object that the default I/O request arrives from. 


### -param pWdfRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface that represents the framework request object. 


## -returns



None




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556843">IQueueCallbackDefaultIoHandler</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556843">IQueueCallbackDefaultIoHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>
 

 

