---
UID: NN:wdtfpnpaction.IWDTFPNPAction2
title: IWDTFPNPAction2
author: windows-driver-content
description: Defines operations and properties for the Plug and Play (PNP) device-related test interfaces.
old-location: dtf\iwdtfpnpaction2.htm
old-project: dtf
ms.assetid: 02eb7351-fde0-4738-be96-53f8cda67d40
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], IWDTFPNPAction2 interface [Windows Device Testing Framework], described, Microsoft.WDTF.IWDTFPNPAction2, dtf.iwdtfpnpaction2, wdtfpnpaction/IWDTFPNPAction2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPNPAction.Interop.dll
req.type-library: 
req.lib: wdtfpnpaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverPNPAction.Interop.dll
apiname:
-	IWDTFPNPAction2
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPAction2 interface


## -description


Defines operations and properties for the Plug and Play (PNP) device-related test interfaces.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFPNPAction2</b> interface inherits from <b>IWDTFActionWithCustomActions2</b>. <b>IWDTFPNPAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFPNPAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451096">DisableDevice</a>
</td>
<td align="left" width="63%">
Disables the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451099">EDTCancelRemoveDevice</a>
</td>
<td align="left" width="63%">
Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451073">EDTCancelStopDevice</a>
</td>
<td align="left" width="63%">
Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451075">EDTSurpriseRemoveDevice</a>
</td>
<td align="left" width="63%">
Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451077">EDTTryStopDevice</a>
</td>
<td align="left" width="63%">
Attempts to send an IRP_MN_STOP_DEVICE event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451079">EDTTryStopDeviceFailRestart</a>
</td>
<td align="left" width="63%">
Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
then fail the subsequent device restart.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451081">EDTTryStopDeviceRequestNewResources</a>
</td>
<td align="left" width="63%">
Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
assign new resources to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451082">EnableDevice</a>
</td>
<td align="left" width="63%">
Enables the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451084">RemoveDevice</a>
</td>
<td align="left" width="63%">
Removes the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451139">RequestEjectDevice</a>
</td>
<td align="left" width="63%">
Initiates a device eject.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451088">RescanDevice</a>
</td>
<td align="left" width="63%">
Rescans the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451090">RescanParentDevice</a>
</td>
<td align="left" width="63%">
Rescans and re-enumerates the target device's parent device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451147">RestartDevice</a>
</td>
<td align="left" width="63%">
Initiates a device restart.

</td>
</tr>
</table> 

