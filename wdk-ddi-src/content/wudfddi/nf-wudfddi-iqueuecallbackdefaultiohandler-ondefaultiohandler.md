---
UID: NF:wudfddi.IQueueCallbackDefaultIoHandler.OnDefaultIoHandler
title: IQueueCallbackDefaultIoHandler::OnDefaultIoHandler method
author: windows-driver-content
description: The OnDefaultIoHandler method handles I/O requests that no other method is registered to handle.
old-location: wdf\iqueuecallbackdefaultiohandler_ondefaultiohandler.htm
old-project: wdf
ms.assetid: d0973dc9-58d6-486f-860e-a891600be73e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: UMDFQueueObjectRef_21f994ea-feca-4c50-aa83-401581713c3f.xml, wudfddi/IQueueCallbackDefaultIoHandler::OnDefaultIoHandler, umdf.iqueuecallbackdefaultiohandler_ondefaultiohandler, OnDefaultIoHandler, OnDefaultIoHandler method, IQueueCallbackDefaultIoHandler interface, IQueueCallbackDefaultIoHandler::OnDefaultIoHandler, IQueueCallbackDefaultIoHandler, wdf.iqueuecallbackdefaultiohandler_ondefaultiohandler, OnDefaultIoHandler method, IQueueCallbackDefaultIoHandler interface, OnDefaultIoHandler method
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
req.lib: wudfddi.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IQueueCallbackDefaultIoHandler.OnDefaultIoHandler
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IQueueCallbackDefaultIoHandler::OnDefaultIoHandler method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDefaultIoHandler</b> method handles I/O requests that no other method is registered to handle. 


## -syntax


````
void OnDefaultIoHandler(
  [in] IWDFIoQueue   *pWdfQueue,
  [in] IWDFIoRequest *pWdfRequest
);
````


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue object that the default I/O request arrives from. 


### -param pWdfRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface that represents the framework request object. 


## -returns


None



## -remarks


A driver registers the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackdefaultiohandler.md">IQueueCallbackDefaultIoHandler</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>

<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdefaultiohandler.md">IQueueCallbackDefaultIoHandler</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IQueueCallbackDefaultIoHandler::OnDefaultIoHandler method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

