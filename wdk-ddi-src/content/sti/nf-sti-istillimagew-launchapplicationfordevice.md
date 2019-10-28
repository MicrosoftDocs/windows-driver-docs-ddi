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
f1_keywords:
 - "sti/IStillImageW.LaunchApplicationForDevice"
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

The **IStillImage::LaunchApplicationForDevice** method starts a specified application for a specified still image device.

## -parameters

### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling [IStillImage::GetSTILaunchInformation](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)) or [IStillImage::GetDeviceList](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)).

### -param pwszAppName [in]

Caller-supplied pointer to a string representing the short name of an application that was registered by calling [IStillImage::RegisterLaunchApplication](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543798(v=vs.85)).

### -param pStiNotify [in]

Caller-supplied pointer to an [STINOTIFY](https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/ns-sti-_stinotify) structure describing a device event. Typically,  the event's GUID is obtained by calling [IStiDevice::GetLastNotificationData](https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-getlastnotificationdata).

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

The **IStillImage::LaunchApplicationForDevice** method can only start applications that have registered themselves by calling [IStillImage::RegisterLaunchApplication](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543798(v=vs.85)). The specified event must be one that the specified device supports. The method mimics the occurrence of a device event, and is useful for applications that intercept events from devices and reroute them. (When a user starts the scanner, such an application might, for example, ask the user whether she wants to store the scanned image, make a copy, or send a fax.)

Before calling **IStillImage::LaunchApplicationForDevice**, clients of the **IStillImage** COM interface must call [IStillImage::StiCreateInstance](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)) to obtain an **IStillImage** interface pointer.

### Examples

```cpp
HRESULT hRes;
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
}
```
