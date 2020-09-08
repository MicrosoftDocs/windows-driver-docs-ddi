---
UID: NF:sti.IStillImageW.EnableHwNotifications
title: IStillImageW::EnableHwNotifications (sti.h)
description: The IStillImage::EnableHwNotifications method requests the still image event monitor to enable or disable the notification of applications when Still Image Device Events occur for a specified device.
old-location: image\istillimage_enablehwnotifications.htm
tech.root: image
ms.assetid: 54b4468a-7823-4afe-8845-696c4a534367
ms.date: 05/03/2018
keywords: ["IStillImageW::EnableHwNotifications"]
ms.keywords: EnableHwNotifications, EnableHwNotifications method [Imaging Devices], EnableHwNotifications method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],EnableHwNotifications method, IStillImageW.EnableHwNotifications, IStillImageW::EnableHwNotifications, image.istillimage_enablehwnotifications, sti/IStillImageW::EnableHwNotifications, stifnc_50df840a-7fa2-4235-864f-dee8ce5ce849.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IStillImageW::EnableHwNotifications
 - sti/IStillImageW::EnableHwNotifications
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW.EnableHwNotifications
---

# IStillImageW::EnableHwNotifications


## -description

The <b>IStillImage::EnableHwNotifications</b> method requests the still image event monitor to enable or disable the notification of applications when <a href="https://docs.microsoft.com/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> occur for a specified device.

## -parameters

### -param pwszDeviceName 

[in]
Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a> or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>.

### -param bNewState

Caller-supplied value, set to <b>TRUE</b> to enable notifications and <b>FALSE</b> to disable them.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStillImage::EnableHwNotifications</b> method enables or disables notifications of still image device events for <i>all</i> applications, not just for the calling application. Event notifications are enabled by default. This method is meant for use by applications that intercept events from devices and reroute them.

Before calling <b>IStillImage::EnableHwNotifications</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543796(v=vs.85)">IStillImage::LaunchApplicationForDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStillImageW</a>

