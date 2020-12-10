---
UID: NN:wudfddi.IQueueCallbackIoResume
title: IQueueCallbackIoResume (wudfddi.h)
description: The IQueueCallbackIoResume interface contains a method that resumes the processing of an I/O request from a queue.
old-location: wdf\iqueuecallbackioresume.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IQueueCallbackIoResume interface"]
ms.keywords: IQueueCallbackIoResume, IQueueCallbackIoResume interface, IQueueCallbackIoResume interface,described, UMDFQueueObjectRef_3ee832e4-15ba-4c39-bb77-38ebbc91983d.xml, umdf.iqueuecallbackioresume, wdf.iqueuecallbackioresume, wudfddi/IQueueCallbackIoResume
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IQueueCallbackIoResume
 - wudfddi/IQueueCallbackIoResume
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wudfddi.h
api_name:
 - IQueueCallbackIoResume
---

# IQueueCallbackIoResume interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IQueueCallbackIoResume</b> interface contains a method that resumes the processing of an I/O request from a queue.

A driver registers the <b>IQueueCallbackIoResume</b> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackIoResume</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IQueueCallbackIoResume</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
