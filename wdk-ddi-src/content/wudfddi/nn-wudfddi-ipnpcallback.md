---
UID: NN:wudfddi.IPnpCallback
title: IPnpCallback
author: windows-driver-content
description: The IPnpCallback interface is a Plug and Play (PnP) and power management (PM) interface.
old-location: wdf\ipnpcallback.htm
tech.root: wdf
ms.assetid: b6ab28e1-08d5-49ee-931a-8e2fe68bd75e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallback, IPnpCallback interface, IPnpCallback interface,described, UMDFDeviceObjectRef_1e101e13-802b-4196-a76c-ed4103d6fbe3.xml, umdf.ipnpcallback, wdf.ipnpcallback, wudfddi/IPnpCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
-	IPnpCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallback interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IPnpCallback</b> interface is a Plug and Play (PnP) and power management (PM) interface. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallback</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPnpCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPnpCallback</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/6efa3d8e-3e54-4ab1-82e0-08ba12bb1877">OnD0Entry</a> method notifies a driver when a device enters the D0 power state so that the driver can perform necessary operations, such as enabling the device. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556803">IPnpCallback::OnD0Exit</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/39eedeca-269d-4966-be1f-7cc5c9228a5c">OnD0Exit</a> method notifies a driver when a device exits the D0 power state so that the driver can perform necessary operations,  such as disabling the device. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556808">IPnpCallback::OnQueryRemove</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/ae95a22d-7b5b-4854-b2f5-76b46cf268f9">OnQueryRemove</a> method notifies a driver before a device is removed from a computer. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556811">IPnpCallback::OnQueryStop</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/e0cb14fa-82d0-4ce3-8672-801e7f04d522">OnQueryStop</a> method notifies a driver before a device is stopped. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556812">IPnpCallback::OnSurpriseRemoval</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/4289406f-dda0-4439-be6e-6e638bb46e1f">OnSurpriseRemoval</a> method notifies a driver after a device is removed from a computer unexpectedly so that the driver can perform necessary operations.

</td>
</tr>
</table> 


## -remarks



A driver registers the <b>IPnpCallback</b> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 



