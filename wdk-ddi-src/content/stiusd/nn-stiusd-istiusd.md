---
UID: NN:stiusd.IStiUSD
title: IStiUSD (stiusd.h)
description: This section describes the methods defined for the IStiUSD COM Interface. Method prototypes are contained in Stiusd.h.
old-location: image\istiusd_interface_methods.htm
tech.root: image
ms.assetid: 62740263-5bbb-48e1-be3d-9ee9cb37d6b9
ms.date: 05/03/2018
ms.keywords: IStiUSD, IStiUSD interface [Imaging Devices], IStiUSD interface [Imaging Devices],described, image.istiusd_interface_methods, stifnc_2fa7c229-f4c5-455e-ba93-019c5b84dd79.xml, stiusd/IStiUSD
ms.topic: interface
f1_keywords:
 - "stiusd/IStiUSD"
req.header: stiusd.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
- stiusd.h
api_name:
- IStiUSD
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiUSD interface


## -description



This section describes the methods defined for the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istiusd-com-interface">IStiUSD COM Interface</a>. Method prototypes are contained in <i>Stiusd.h</i>.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IStiUSD</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IStiUSD</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IStiUSD</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pdevice_reset_handler">DeviceReset</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::DeviceReset</b> method resets a still image device to a known, initialized state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-diagnostic">Diagnostic</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::Diagnostic</b> method runs diagnostic tests on a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/Microsoft-Windows-Embedded-KeyboardFilterService-escape">Escape</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::Escape</b> method performs a vendor-specific I/O operation on a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getcapabilities">GetCapabilities</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::GetCapabilities</b> method returns a still image device's capabilities.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-getlasterror">GetLastError</a>
</td>
<td align="left" width="63%">
The <b>IStiUSD::GetLastError</b> method returns the last known error associated with a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-getlasterrorinfo">GetLastErrorInfo</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-getnotificationdata">GetNotificationData</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::GetNotificationData</b> method returns a description of the most recent event that occurred on a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfaction2-getstatus">GetStatus</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::GetStatus</b> method returns the status of a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff550945(v=vs.85)">Initialize</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::Initialize</b> method initializes an instance of the COM object that defines the <b>IStiUSD</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-lockdevice">LockDevice</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::LockDevice</b> method locks a device for exclusive use by the caller.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-rawreadcommand">RawReadCommand</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::RawReadCommand</b> method reads command information from a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-rawreaddata">RawReadData</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::RawReadData</b> method reads data from a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-rawwritecommand">RawWriteCommand</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiDevice::RawWriteCommand</b> method sends command information to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-rawwritedata">RawWriteData</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::RawWriteData</b> method writes data to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-setnotificationhandle">SetNotificationHandle</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::SetNotificationHandle</b> method specifies an event handle that the minidriver should use to inform the caller of device events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-unlockdevice">UnLockDevice</a>
</td>
<td align="left" width="63%">
A still image minidriver's <b>IStiUSD::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-lockdevice">IStiUSD::LockDevice</a>.

</td>
</tr>
</table> 

