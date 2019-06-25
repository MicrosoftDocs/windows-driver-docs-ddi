---
UID: NF:sti.IStillImageW.LaunchApplicationForDevice
title: IStillImageW::LaunchApplicationForDevice (sti.h)
description: The IStillImage::LaunchApplicationForDevice method starts a specified application for a specified still image device.
old-location: image\istillimage_launchapplicationfordevice.htm
tech.root: image
ms.assetid: e5bb8d0e-9ae0-42dd-bbd0-c12e3d1e3f40
ms.date: 05/03/2018
ms.keywords: IStillImageW interface [Imaging Devices],LaunchApplicationForDevice method, IStillImageW.LaunchApplicationForDevice, IStillImageW::LaunchApplicationForDevice, LaunchApplicationForDevice, LaunchApplicationForDevice method [Imaging Devices], LaunchApplicationForDevice method [Imaging Devices],IStillImageW interface, image.istillimage_launchapplicationfordevice, sti/IStillImageW::LaunchApplicationForDevice, stifnc_3ecda881-3b82-4323-b739-614e4f8f78a7.xml
ms.topic: method
req.header: sti.h
req.include-header: Sti.h
req.target-type: Desktop
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
- sti.h
api_name:
- IStillImageW.LaunchApplicationForDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::LaunchApplicationForDevice


## -description


The <b>IStillImage::LaunchApplicationForDevice</b> method starts a specified application for a specified still image device.


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a> or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>.


### -param pwszAppName [in]

Caller-supplied pointer to a string representing the short name of an application that was registered by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543798(v=vs.85)">IStillImage::RegisterLaunchApplication</a>.


### -param pStiNotify [in]

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/ns-sti-_stinotify">STINOTIFY</a> structure describing a device event. Typically,  the event's GUID is obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-getlastnotificationdata">IStiDevice::GetLastNotificationData</a>.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStillImage::LaunchApplicationForDevice</b> method can only start applications that have registered themselves by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543798(v=vs.85)">IStillImage::RegisterLaunchApplication</a>. The specified event must be one that the specified device supports. The method mimics the occurrence of a device event, and is useful for applications that intercept events from devices and reroute them. (When a user starts the scanner, such an application might, for example, ask the user whether she wants to store the scanned image, make a copy, or send a fax.)

Before calling <b>IStillImage::LaunchApplicationForDevice</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT hRes;
hRes = pStiDevice->GetLastNotificationData(&pNotify);
if (!SUCCEEDED(hRes))
{
    DisplayOutput("->GetLastNotificationData returned %xh %u",
        hReturn,hReturn);
}
 
// Process or filter events here
 
// Send event on to app
hRes = pSti->LaunchApplicationForDevice(pStiInfoPtr->szDeviceInternalName,
     L"AppName",
     pNotify);
if (!SUCCEEDED(hRes))
{
    DisplayOutput("->LaunchApplicationForDevice on %S returned %xh %u",
        pStiInfoPtr->szDeviceInternalName,hReturn,hReturn);
}</pre>
</td>
</tr>
</table></span></div>


