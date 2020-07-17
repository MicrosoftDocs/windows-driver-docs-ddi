---
UID: NN:wudfddi.IQueueCallbackIoStop
title: IQueueCallbackIoStop (wudfddi.h)
description: The IQueueCallbackIoStop interface contains a method that stops the processing of an I/O request from a queue.
old-location: wdf\iqueuecallbackiostop.htm
tech.root: wdf
ms.assetid: 430ee7fd-cffb-452d-b2e8-0dc252987487
ms.date: 02/26/2018
keywords: ["IQueueCallbackIoStop interface"]
ms.keywords: IQueueCallbackIoStop, IQueueCallbackIoStop interface, IQueueCallbackIoStop interface,described, UMDFQueueObjectRef_cf62ed54-43d3-4a9e-8e82-85695bf30527.xml, umdf.iqueuecallbackiostop, wdf.iqueuecallbackiostop, wudfddi/IQueueCallbackIoStop
f1_keywords:
 - "wudfddi/IQueueCallbackIoStop"
 - "IQueueCallbackIoStop"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wudfddi.h
api_name:
- IQueueCallbackIoStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackIoStop interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IQueueCallbackIoStop</b> interface contains a method that stops the processing of an I/O request from a queue.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackIoStop</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IQueueCallbackIoStop</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



A driver registers the <b>IQueueCallbackIoStop</b> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 



