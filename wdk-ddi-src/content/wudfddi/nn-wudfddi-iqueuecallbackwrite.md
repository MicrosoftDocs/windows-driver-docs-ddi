---
UID: NN:wudfddi.IQueueCallbackWrite
title: IQueueCallbackWrite (wudfddi.h)
description: An I/O queue object notifies a driver when a write request is available for the driver.
old-location: wdf\iqueuecallbackwrite.htm
tech.root: wdf
ms.assetid: 8b44e1e1-c648-4eec-bb3e-ab327dc08f98
ms.date: 02/26/2018
ms.keywords: IQueueCallbackWrite, IQueueCallbackWrite interface, IQueueCallbackWrite interface,described, UMDFQueueObjectRef_4abdce88-185f-4dab-823a-00da96d7d630.xml, umdf.iqueuecallbackwrite, wdf.iqueuecallbackwrite, wudfddi/IQueueCallbackWrite
ms.topic: interface
f1_keywords:
 - "wudfddi/IQueueCallbackWrite"
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
- IQueueCallbackWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackWrite interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue object notifies a driver when a write request is available for the driver. The I/O queue object notifies the driver when an application calls the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. The driver can handle the notification by registering the <b>IQueueCallbackWrite</b> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackWrite</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IQueueCallbackWrite</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IQueueCallbackWrite</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackwrite-onwrite">IQueueCallbackWrite::OnWrite</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackwrite-onwrite">OnWrite</a> method is called to handle a write request when an application writes information to a device through the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. 

</td>
</tr>
</table> 


## -remarks



A driver registers the <b>IQueueCallbackWrite</b> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. For more information about creating or configuring I/O queues, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">Configuring Dispatch Mode for an I/O Queue</a>.



