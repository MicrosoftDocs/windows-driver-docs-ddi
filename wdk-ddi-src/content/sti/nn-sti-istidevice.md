---
UID: NN:sti.IStiDevice
title: IStiDevice (sti.h)
description: This section describes the methods defined for the IStiDevice COM Interface. Method prototypes are contained in Sti.h.
old-location: image\istidevice_interface_methods.htm
tech.root: image
ms.assetid: 86ce412e-007b-4ea9-9c09-766eee543852
ms.date: 05/03/2018
ms.keywords: IStiDevice, IStiDevice interface [Imaging Devices], IStiDevice interface [Imaging Devices],described, image.istidevice_interface_methods, sti/IStiDevice, stifnc_ef9e9c06-e918-462c-92c0-f4b1605a0847.xml
ms.topic: interface
req.header: sti.h
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
- sti.h
api_name:
- IStiDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiDevice interface


## -description


This section describes the methods defined for the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istidevice-com-interface">IStiDevice COM Interface</a>. Method prototypes are contained in <i>Sti.h</i>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IStiDevice</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IStiDevice</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IStiDevice</b> interface has these methods.
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
The <b>IStiDevice::DeviceReset</b> method resets a still image device to a known state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-diagnostic">Diagnostic</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Diagnostic</b> method executes diagnostic tests on a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/Microsoft-Windows-Embedded-KeyboardFilterService-escape">Escape</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Escape</b> method sends a request for a vendor-specific I/O operation to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getcapabilities">GetCapabilities</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetCapabilities</b> method returns a still image device's capabilities.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-getlasterror">GetLastError</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetLastError</b> method returns the last known error associated with a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-getlasterrorinfo">GetLastErrorInfo</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-getlastnotificationdata">GetLastNotificationData</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetLastNotificationData</b> method returns a description of the most recent event that occurred on a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfaction2-getstatus">GetStatus</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetStatus</b> method returns a still image device's status information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff550945(v=vs.85)">Initialize</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Initialize</b> method initializes an instance of the COM object that defines the <b>IStiDevice</b> interface. <i>This method is for internal use only</i>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-rawwritecommand">IStiDevice::RawWriteCommand</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawWriteCommand</b> method sends command information to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-rawwritedata">IStiDevice::RawWriteData</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawWriteData</b> method writes data to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-release">IStiDevice::Release</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a>, and removes access to the object's interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-lockdevice">LockDevice</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::LockDevice </b>method locks a device for exclusive use by the caller.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-rawreadcommand">RawReadCommand</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawReadCommand</b> method reads command information from a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-rawreaddata">RawReadData</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawReadData</b> method reads data from a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-subscribe">Subscribe</a>
</td>
<td align="left" width="63%">
The<b> IStiDevice::Subscribe</b> method registers the caller to receive notifications of device events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-unlockdevice">UnLockDevice</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-unsubscribe">UnSubscribe</a>
</td>
<td align="left" width="63%">
The<b> IStiDevice::UnSubscribe</b> method removes the caller from the list of applications registered to receive notification of device events.

</td>
</tr>
</table> 

