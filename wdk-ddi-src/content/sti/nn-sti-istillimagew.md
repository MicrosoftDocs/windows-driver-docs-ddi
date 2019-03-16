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



This section describes the methods defined for the <a href="https://msdn.microsoft.com/eb60a3fd-e7e2-4d3c-973e-af8cb3c3c511">IStillImage COM Interface</a>. Method prototypes are contained in <i>S</i><i>ti.h</i>.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IStillImageW</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IStillImageW</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/24491434-1ad2-48fa-85e6-516efbe0550d">CreateDevice</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::CreateDevice</b> method creates an instance of the COM object that defines the <a href="https://msdn.microsoft.com/b026fb74-9ce6-4d4e-8a5b-402731904064">IStiDevice COM Interface</a>, and returns a pointer to the interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/54b4468a-7823-4afe-8845-696c4a534367">EnableHwNotifications</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::EnableHwNotifications</b> method requests the still image event monitor to enable or disable the notification of applications when <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a> occur for a specified device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4f3e1dcd-1885-4b9f-b033-19d91178d8ab">GetDeviceInfo</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetDeviceInfo</b> method returns hardware characteristics for a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/43c8a5d2-7f34-4b68-b316-020049e98444">GetDeviceList</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetDeviceList</b> method returns hardware characteristics for all installed still image devices.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/506c50fa-f162-4b30-bfb9-91987e064c39">GetDeviceValue</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetDeviceValue</b> method returns registry information associated with a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/8c97c4f0-3cb8-4457-8389-02d9fba51400">GetHwNotificationState</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetHwNotificationState</b> method indicates whether applications will be notified when <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a> occur on a specified device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/cfcd6e2d-541a-4a28-b2c7-409eb10bcf1e">GetSTILaunchInformation</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::GetSTILaunchInformation</b> method returns the reason the calling still image application was started, if the still image event monitor started it.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550945">Initialize</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::Initialize</b> method initializes an instance of the COM object that defines the <b>IStillImage</b> COM interface. <i>This method is for internal system use only</i>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e5bb8d0e-9ae0-42dd-bbd0-c12e3d1e3f40">LaunchApplicationForDevice</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::LaunchApplicationForDevice</b> method starts a specified application for a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b76f2f3d-46ff-4a85-b3b2-1924946fa45d">RegisterLaunchApplication</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::RegisterLaunchApplication</b> method adds an application to the still image event monitor's list of push-model aware applications.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/3c595531-a1b0-48a5-867c-f1e6558e46ff">Release</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a>, and removes access to the object's interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e2ea9c59-cc63-4ced-a225-e0c9667dd574">SetDeviceValue</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::SetDeviceValue</b> method sets registry information for a specified still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/8fbbe6c8-bf65-42df-a4e4-cb683b567bf7">SetupDeviceParameters</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::SetupDeviceParameters</b> method allows clients of the <b>IStillImage</b> COM interface to modify a still image device's stored characteristics, if the device's bus type is unknown.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a3d4ef45-d541-40f2-ad0b-cb8720438886">StiCreateInstanceW</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::StiCreateInstance</b> method creates an instance of the COM object that defines the <b>IStillImage</b> interface, and returns a pointer to the interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/cf57265a-d343-4e49-9635-6a4663c9a3a5">UnregisterLaunchApplication</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::UnregisterLaunchApplication</b> method removes an application from the still image event monitor's list of push-model aware applications.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/24795026-41bc-447e-812f-8fc3a1c573b9">WriteToErrorLog</a>
</td>
<td align="left" width="63%">
The <b>IStillImage::WriteToErrorLog </b>method writes a message to the still image error log.

</td>
</tr>
</table> 

