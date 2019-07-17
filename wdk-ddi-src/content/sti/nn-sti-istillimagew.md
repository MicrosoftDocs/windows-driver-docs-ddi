---
UID: NN:sti.IStillImageW
title: IStillImageW (sti.h)
description: This section describes the methods defined for the IStillImage COM Interface. Method prototypes are contained in Sti.h.
old-location: image\istillimage_interface_methods.htm
tech.root: image
ms.assetid: a9ceee48-cbb5-4448-83b4-9c19fe89fcb9
ms.date: 05/03/2018
ms.keywords: IStillImageW, IStillImageW interface [Imaging Devices], IStillImageW interface [Imaging Devices],described, image.istillimage_interface_methods, sti/IStillImageW, stifnc_a737fc11-5690-49a8-b64e-82b27bb55e52.xml
ms.topic: interface
f1_keywords:
 - "sti/IStillImageW"
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
- IStillImageW
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW interface


## -description



This section describes the methods defined for the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istillimage-com-interface">IStillImage COM Interface</a>. Method prototypes are contained in <i>S</i><i>ti.h</i>.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IStillImageW</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IStillImageW</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IStillImageW</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">CreateDevice</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::CreateDevice</b> method creates an instance of the COM object that defines the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istidevice-com-interface">IStiDevice COM Interface</a>, and returns a pointer to the interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543780(v=vs.85)">EnableHwNotifications</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::EnableHwNotifications</b> method requests the still image event monitor to enable or disable the notification of applications when <a href="https://docs.microsoft.com/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> occur for a specified device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543782(v=vs.85)">GetDeviceInfo</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetDeviceInfo</b> method returns hardware characteristics for a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">GetDeviceList</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetDeviceList</b> method returns hardware characteristics for all installed still image devices.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543786(v=vs.85)">GetDeviceValue</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetDeviceValue</b> method returns registry information associated with a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543788(v=vs.85)">GetHwNotificationState</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetHwNotificationState</b> method indicates whether applications will be notified when <a href="https://docs.microsoft.com/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> occur on a specified device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">GetSTILaunchInformation</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetSTILaunchInformation</b> method returns the reason the calling still image application was started, if the still image event monitor started it.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff550945(v=vs.85)">Initialize</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::Initialize</b> method initializes an instance of the COM object that defines the <b>IStillImage</b> COM interface. <i>This method is for internal system use only</i>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543796(v=vs.85)">LaunchApplicationForDevice</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::LaunchApplicationForDevice</b> method starts a specified application for a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543798(v=vs.85)">RegisterLaunchApplication</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::RegisterLaunchApplication</b> method adds an application to the still image event monitor's list of push-model aware applications.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543799(v=vs.85)">Release</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a>, and removes access to the object's interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543801(v=vs.85)">SetDeviceValue</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::SetDeviceValue</b> method sets registry information for a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543803(v=vs.85)">SetupDeviceParameters</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::SetupDeviceParameters</b> method allows clients of the <b>IStillImage</b> COM interface to modify a still image device's stored characteristics, if the device's bus type is unknown.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">StiCreateInstanceW</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::StiCreateInstance</b> method creates an instance of the COM object that defines the <b>IStillImage</b> interface, and returns a pointer to the interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543806(v=vs.85)">UnregisterLaunchApplication</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::UnregisterLaunchApplication</b> method removes an application from the still image event monitor's list of push-model aware applications.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543807(v=vs.85)">WriteToErrorLog</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::WriteToErrorLog </b>method writes a message to the still image error log.

</td>
</tr>
</table> 

