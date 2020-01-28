---
UID: NN:wudfddi.IQueueCallbackStateChange
title: IQueueCallbackStateChange (wudfddi.h)
description: An I/O queue object raises an event when it changes state. A driver can consume the event by registering the IQueueCallbackStateChange interface.
old-location: wdf\iqueuecallbackstatechange.htm
tech.root: wdf
ms.assetid: 39c66462-015d-49ba-9a37-0b3b928e5fbf
ms.date: 02/26/2018
ms.keywords: IQueueCallbackStateChange, IQueueCallbackStateChange interface, IQueueCallbackStateChange interface,described, UMDFQueueObjectRef_57a57868-6a9d-42b3-8c74-ceb6c4be03c3.xml, umdf.iqueuecallbackstatechange, wdf.iqueuecallbackstatechange, wudfddi/IQueueCallbackStateChange
f1_keywords:
 - "wudfddi/IQueueCallbackStateChange"
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
- IQueueCallbackStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackStateChange interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue object raises an event when it changes state. A driver can consume the event by registering the <b>IQueueCallbackStateChange</b> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackStateChange</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IQueueCallbackStateChange</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



A driver registers the <b>IQueueCallbackStateChange</b> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 



