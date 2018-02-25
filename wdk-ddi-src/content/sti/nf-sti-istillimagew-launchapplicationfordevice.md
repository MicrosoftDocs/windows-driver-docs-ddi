---
UID: NF:sti.IStillImageW.LaunchApplicationForDevice
title: IStillImageW::LaunchApplicationForDevice method
author: windows-driver-content
description: The IStillImage::LaunchApplicationForDevice method starts a specified application for a specified still image device.
old-location: image\istillimage_launchapplicationfordevice.htm
old-project: image
ms.assetid: e5bb8d0e-9ae0-42dd-bbd0-c12e3d1e3f40
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, A, D, F, I, IStillImage interface [Imaging Devices], LaunchApplicationForDevice method, IStillImage::LaunchApplicationForDevice, IStillImageW, IStillImageW::LaunchApplicationForDevice, L, LaunchApplicationForDevice method [Imaging Devices], LaunchApplicationForDevice method [Imaging Devices], IStillImage interface, LaunchApplicationForDevice,IStillImageW.LaunchApplicationForDevice, S, W, a, c, e, g, h, i, image.istillimage_launchapplicationfordevice, l, m, n, o, p, r, sti/IStillImage::LaunchApplicationForDevice, stifnc_3ecda881-3b82-4323-b739-614e4f8f78a7.xml, t, u, v"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	sti.h
apiname:
-	IStillImage.LaunchApplicationForDevice
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::LaunchApplicationForDevice method


## -description


The <b>IStillImage::LaunchApplicationForDevice</b> method starts a specified application for a specified still image device.


## -syntax


````
HRESULT LaunchApplicationForDevice(
  [in] LPWSTR      pwszDeviceName,
  [in] LPWSTR      pwszAppName,
  [in] LPSTINOTIFY pStiNotify
);
````


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.


### -param pwszAppName [in]

Caller-supplied pointer to a string representing the short name of an application that was registered by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543798">IStillImage::RegisterLaunchApplication</a>.


### -param pStiNotify [in]

Caller-supplied pointer to an <a href="..\sti\ns-sti-_stinotify.md">STINOTIFY</a> structure describing a device event. Typically,  the event's GUID is obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543751">IStiDevice::GetLastNotificationData</a>.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStillImage::LaunchApplicationForDevice</b> method can only start applications that have registered themselves by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543798">IStillImage::RegisterLaunchApplication</a>. The specified event must be one that the specified device supports. The method mimics the occurrence of a device event, and is useful for applications that intercept events from devices and reroute them. (When a user starts the scanner, such an application might, for example, ask the user whether she wants to store the scanned image, make a copy, or send a fax.)

Before calling <b>IStillImage::LaunchApplicationForDevice</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT hRes;
hRes = pStiDevice-&gt;GetLastNotificationData(&amp;pNotify);
if (!SUCCEEDED(hRes))
{
    DisplayOutput("-&gt;GetLastNotificationData returned %xh %u",
        hReturn,hReturn);
}
 
// Process or filter events here
 
// Send event on to app
hRes = pSti-&gt;LaunchApplicationForDevice(pStiInfoPtr-&gt;szDeviceInternalName,
     L"AppName",
     pNotify);
if (!SUCCEEDED(hRes))
{
    DisplayOutput("-&gt;LaunchApplicationForDevice on %S returned %xh %u",
        pStiInfoPtr-&gt;szDeviceInternalName,hReturn,hReturn);
}</pre>
</td>
</tr>
</table></span></div>


