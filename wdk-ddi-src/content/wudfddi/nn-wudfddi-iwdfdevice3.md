---
UID: NN:wudfddi.IWDFDevice3
title: IWDFDevice3
author: windows-driver-content
description: To obtain the IWDFDevice3 interface, drivers call IWDFDevice::QueryInterface.
old-location: wdf\iwdfdevice3.htm
old-project: wdf
ms.assetid: C4AEC0DA-EB93-481D-A94C-7BB7BF15EFBC
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfdevice3, IWDFDevice3 interface, IWDFDevice3 interface, described, IWDFDevice3, wudfddi/IWDFDevice3, umdf.iwdfdevice3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	WUDFx.dll
apiname:
-	IWDFDevice3
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice3 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFDevice3</b> interface, drivers call <b>IWDFDevice::QueryInterface</b>.


## -members

The <b>IWDFDevice3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451202">AssignS0IdleSettingsEx</a>
</td>
<td align="left" width="63%">
The 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451202">AssignS0IdleSettingsEx</a> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451208">CreateInterrupt</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451208">CreateInterrupt</a> method creates a framework interrupt object.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451213">CreateWorkItem</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451213">CreateWorkItem</a> method creates a framework work-item object, which can subsequently be added to the framework’s work-item queue.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451219">GetHardwareRegisterMappedAddress</a>
</td>
<td align="left" width="63%">
A driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451219">GetHardwareRegisterMappedAddress</a> to get the user-mode mapped address of the memory resource it earlier mapped using <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> method maps the given physical address range to system address space and returns a pseudo base address. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/19B472D0-D607-4874-ADB9-232C379B0DFD">ReadFromHardware</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/19B472D0-D607-4874-ADB9-232C379B0DFD">ReadFromHardware</a> method is used internally by the framework. Do not use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451237">UnmapIoSpace</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451237">UnmapIoSpace</a> method unmaps a specified range of physical addresses previously mapped by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/55FBE72C-E74E-4116-9602-6D491592350F">WriteToHardware</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/55FBE72C-E74E-4116-9602-6D491592350F">WriteToHardware</a> method is used internally by the framework. Do not use.

</td>
</tr>
</table>The 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451202">AssignS0IdleSettingsEx</a> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451208">CreateInterrupt</a> method creates a framework interrupt object.


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451213">CreateWorkItem</a> method creates a framework work-item object, which can subsequently be added to the framework’s work-item queue.

A driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451219">GetHardwareRegisterMappedAddress</a> to get the user-mode mapped address of the memory resource it earlier mapped using <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> method maps the given physical address range to system address space and returns a pseudo base address. 

The <a href="https://msdn.microsoft.com/19B472D0-D607-4874-ADB9-232C379B0DFD">ReadFromHardware</a> method is used internally by the framework. Do not use.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451237">UnmapIoSpace</a> method unmaps a specified range of physical addresses previously mapped by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> method.

The <a href="https://msdn.microsoft.com/55FBE72C-E74E-4116-9602-6D491592350F">WriteToHardware</a> method is used internally by the framework. Do not use.

 


## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3 interface%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

