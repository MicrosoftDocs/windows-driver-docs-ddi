---
UID: NN:wudfddi.IQueueCallbackDefaultIoHandler
title: IQueueCallbackDefaultIoHandler
author: windows-driver-content
description: The IQueueCallbackDefaultIoHandler interface contains a method that handles I/O requests that no other method is registered to handle.
old-location: wdf\iqueuecallbackdefaultiohandler.htm
old-project: wdf
ms.assetid: 3b2980f9-2f55-4fe3-99ac-1da578688f4b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.iqueuecallbackdefaultiohandler, IQueueCallbackDefaultIoHandler interface, IQueueCallbackDefaultIoHandler interface, described, IQueueCallbackDefaultIoHandler, wudfddi/IQueueCallbackDefaultIoHandler, UMDFQueueObjectRef_31f05689-d38c-444b-b930-9c6c5136c60d.xml, umdf.iqueuecallbackdefaultiohandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
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
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wudfddi.h
apiname:
-	IQueueCallbackDefaultIoHandler
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IQueueCallbackDefaultIoHandler interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IQueueCallbackDefaultIoHandler</b> interface contains a method that handles I/O requests that no other method is registered to handle.


## -members

The <b>IQueueCallbackDefaultIoHandler</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/d0973dc9-58d6-486f-860e-a891600be73e">OnDefaultIoHandler</a> method handles I/O requests that no other method is registered to handle. 

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/d0973dc9-58d6-486f-860e-a891600be73e">OnDefaultIoHandler</a> method handles I/O requests that no other method is registered to handle. 

 


## -remarks



A driver registers the <b>IQueueCallbackDefaultIoHandler</b> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 



