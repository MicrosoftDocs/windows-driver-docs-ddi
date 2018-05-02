---
UID: NN:wudfddi.IWDFIoTargetStateManagement
title: IWDFIoTargetStateManagement
author: windows-driver-content
description: The IWDFIoTargetStateManagement interface exposes methods that manage and monitor the state of an I/O target object.
old-location: wdf\iwdfiotargetstatemanagement.htm
old-project: wdf
ms.assetid: 6870b6fa-1a90-4a7a-935a-4ce8eda940a1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoTargetStateManagement, IWDFIoTargetStateManagement interface, IWDFIoTargetStateManagement interface,described, UMDFIoTargetObjectRef_667496e9-fa1f-4c90-911d-d456ffc3b59e.xml, umdf.iwdfiotargetstatemanagement, wdf.iwdfiotargetstatemanagement, wudfddi/IWDFIoTargetStateManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoTargetStateManagement
product: Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTargetStateManagement interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFIoTargetStateManagement</b> interface exposes methods that manage and monitor the state of an I/O target object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoTargetStateManagement</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IWDFIoTargetStateManagement</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoTargetStateManagement</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559202">IWDFIoTargetStateManagement::GetState</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/f915294f-457f-4913-b4b0-e94e1806a06d">GetState</a> method returns the current state of a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559208">IWDFIoTargetStateManagement::Remove</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439492">Remove</a> method removes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> method starts sending queued requests to a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/dn927275">Stop</a> method stops sending queued requests to a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.

</td>
</tr>
</table> 


## -remarks



Drivers obtain the <b>IWDFIoTargetStateManagement</b> interface by calling <b>IWDFIoTarget::QueryInterface</b>, <b>IWDFUsbTargetPipe::QueryInterface</b>, or <b>IWDFUsbTargetPipe2::QueryInterface</b>.



