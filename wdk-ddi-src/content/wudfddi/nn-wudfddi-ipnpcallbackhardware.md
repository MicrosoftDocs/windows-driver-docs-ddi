---
UID: NN:wudfddi.IPnpCallbackHardware
title: IPnpCallbackHardware (wudfddi.h)
description: The IPnpCallbackHardware interface is a Plug and Play (PnP) and power management (PM) interface.
old-location: wdf\ipnpcallbackhardware.htm
tech.root: wdf
ms.assetid: 2746e7ab-690c-4382-be9a-124a7d68cf72
ms.date: 02/26/2018
ms.keywords: IPnpCallbackHardware, IPnpCallbackHardware interface, IPnpCallbackHardware interface,described, UMDFDeviceObjectRef_4b39ad3c-6fa6-4c47-aba8-676a6f628f1b.xml, umdf.ipnpcallbackhardware, wdf.ipnpcallbackhardware, wudfddi/IPnpCallbackHardware
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackHardware
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackHardware interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IPnpCallbackHardware</b> interface is a Plug and Play (PnP) and power management (PM) interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackHardware</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPnpCallbackHardware</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPnpCallbackHardware</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556766">IPnpCallbackHardware::OnPrepareHardware</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a> method notifies a driver to make the specified hardware accessible.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439739">OnReleaseHardware</a> method notifies a driver to perform operations that are necessary when the specified hardware is no longer accessible.

</td>
</tr>
</table> 


## -remarks



A driver registers the <b>IPnpCallbackHardware</b> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439727">IPnpCallbackHardware2</a>
 

 

