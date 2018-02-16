---
UID: NN:wdtfpnpaction.IWDTFPNPAction2
title: IWDTFPNPAction2
author: windows-driver-content
description: Defines operations and properties for the Plug and Play (PNP) device-related test interfaces.
old-location: dtf\iwdtfpnpaction2.htm
old-project: dtf
ms.assetid: 02eb7351-fde0-4738-be96-53f8cda67d40
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: dtf.iwdtfpnpaction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], IWDTFPNPAction2 interface [Windows Device Testing Framework], described, IWDTFPNPAction2, wdtfpnpaction/IWDTFPNPAction2, Microsoft.WDTF.IWDTFPNPAction2
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
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFPNPAction2 interface


## -description


Defines operations and properties for the Plug and Play (PNP) device-related test interfaces.


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
</table>Disables the target device.

Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device.

Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.

Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.

Attempts to send an IRP_MN_STOP_DEVICE event to the target device.

Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
then fail the subsequent device restart.

Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
assign new resources to the target device.

Enables the target device.

Removes the device.

Initiates a device eject.

Rescans the target device.

Rescans and re-enumerates the target device's parent device.

Initiates a device restart.

 

