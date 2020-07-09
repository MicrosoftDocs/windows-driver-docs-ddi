---
UID: NN:wudfddi.IQueueCallbackIoCanceledOnQueue
title: IQueueCallbackIoCanceledOnQueue (wudfddi.h)
description: The IQueueCallbackIoCanceledOnQueue interface is optional. Your driver can provide this interface if you want UMDF to notify the driver when an I/O request is canceled while it is in the driver's I/O queue.
old-location: wdf\iqueuecallbackiocanceledonqueue.htm
tech.root: wdf
ms.assetid: d85b5c70-4e03-4a12-bc0b-e738d4dab6cf
ms.date: 02/26/2018
keywords: ["IQueueCallbackIoCanceledOnQueue interface"]
ms.keywords: IQueueCallbackIoCanceledOnQueue, IQueueCallbackIoCanceledOnQueue interface, IQueueCallbackIoCanceledOnQueue interface,described, UMDFQueueObjectRef_65c767dc-7b2b-4b25-a546-d0f3fb6fba14.xml, umdf.iqueuecallbackiocanceledonqueue, wdf.iqueuecallbackiocanceledonqueue, wudfddi/IQueueCallbackIoCanceledOnQueue
f1_keywords:
 - "wudfddi/IQueueCallbackIoCanceledOnQueue"
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
- IQueueCallbackIoCanceledOnQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackIoCanceledOnQueue interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IQueueCallbackIoCanceledOnQueue</b> interface is optional. Your driver can provide this interface if you want UMDF to notify the driver when an I/O request is canceled while it is in the driver's I/O queue.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackIoCanceledOnQueue</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IQueueCallbackIoCanceledOnQueue</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



To register an <b>IQueueCallbackIoCanceledOnQueue</b> interface for an I/O queue, the driver must provide a <b>QueryInterface</b> function for the I/O queue object. The <b>QueryInterface</b> function must return a pointer to the <b>IQueueCallbackIoCanceledOnQueue</b> interface. UMDF calls the <b>QueryInterface</b> method of the <b>IUnknown</b> interface that the driver passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>. 



