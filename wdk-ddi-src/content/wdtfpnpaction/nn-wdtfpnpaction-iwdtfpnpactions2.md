---
UID: NN:wdtfpnpaction.IWDTFPNPActions2
title: IWDTFPNPActions2 (wdtfpnpaction.h)
description: Defines operations and properties for the collection of Plug and Play (PNP) device-related test interfaces.
old-location: dtf\iwdtfpnpactions2.htm
tech.root: dtf
ms.assetid: 65f40adc-ec17-4bed-b5b9-e7a5c1c27a6c
ms.date: 04/04/2018
ms.keywords: IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], IWDTFPNPActions2 interface [Windows Device Testing Framework],described, dtf.iwdtfpnpactions2, wdtfpnpaction/IWDTFPNPActions2
ms.topic: interface
f1_keywords:
 - "wdtfpnpaction/IWDTFPNPActions2"
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
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
- wdtfpnpaction.h
api_name:
- IWDTFPNPActions2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFPNPActions2 interface


## -description


Defines operations and properties for the collection of Plug and Play (PNP) device-related test interfaces.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFPNPActions2</b> interface inherits from <b>IWDTFActionsCustom2</b>. <b>IWDTFPNPActions2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFPNPActions2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">DisableDevice</a>
</td>
<td align="left" width="63%">
Disables the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">EDTCancelRemoveDevice</a>
</td>
<td align="left" width="63%">
Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-edtcancelstopdevice">EDTCancelStopDevice</a>
</td>
<td align="left" width="63%">
Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-edtsurpriseremovedevice">EDTSurpriseRemoveDevice</a>
</td>
<td align="left" width="63%">
Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevice">EDTTryStopDevice</a>
</td>
<td align="left" width="63%">
Attempts to send an IRP_MN_STOP_DEVICE event to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevicefailrestart">EDTTryStopDeviceFailRestart</a>
</td>
<td align="left" width="63%">
Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
then fail the subsequent device restart.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevicerequestnewresources">EDTTryStopDeviceRequestNewResources</a>
</td>
<td align="left" width="63%">
Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
assign new resources to the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-enabledevice">EnableDevice</a>
</td>
<td align="left" width="63%">
Enables the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-removedevice">RemoveDevice</a>
</td>
<td align="left" width="63%">
Removes the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">RequestEjectDevice</a>
</td>
<td align="left" width="63%">
Initiates a device eject.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-rescandevice">RescanDevice</a>
</td>
<td align="left" width="63%">
Rescans the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nf-wdtfpnpaction-iwdtfpnpaction2-rescanparentdevice">RescanParentDevice</a>
</td>
<td align="left" width="63%">
Rescans and re-enumerates the target device's parent device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">RestartDevice</a>
</td>
<td align="left" width="63%">
Initiates a device restart.

</td>
</tr>
</table> 

