---
UID: NN:wudfddi.IRemoteInterfaceCallbackEvent
title: IRemoteInterfaceCallbackEvent
author: windows-driver-content
description: The IRemoteInterfaceCallbackEvent interface provides a callback function that the framework calls to notify the driver about device events that are associated with a device interface.
old-location: wdf\iremoteinterfacecallbackevent.htm
tech.root: wdf
ms.assetid: 72b68ed0-d14c-44b1-b848-40c427fe6c9a
ms.date: 02/26/2018
ms.keywords: IRemoteInterfaceCallbackEvent, IRemoteInterfaceCallbackEvent interface, IRemoteInterfaceCallbackEvent interface,described, UMDFIoTargetObjectRef_9ce0aebc-e132-4d0e-b575-7ef1e19d9c30.xml, umdf.iremoteinterfacecallbackevent, wdf.iremoteinterfacecallbackevent, wudfddi/IRemoteInterfaceCallbackEvent
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wudfddi.h
api_name:
-	IRemoteInterfaceCallbackEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRemoteInterfaceCallbackEvent interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IRemoteInterfaceCallbackEvent</b> interface provides a callback function that the framework calls to notify the driver about device events that are associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRemoteInterfaceCallbackEvent</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IRemoteInterfaceCallbackEvent</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IRemoteInterfaceCallbackEvent</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556889">IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent</a>
</td>
<td align="left" width="63%">
A UMDF-based driver's <a href="https://msdn.microsoft.com/6cee6662-2eef-4caf-ab70-780748521ba9">OnRemoteInterfaceEvent</a> event callback function handles device events that are associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>.

</td>
</tr>
</table> 


## -remarks



If your driver supports an <b>IRemoteInterfaceCallbackEvent</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> must return the interface. 



