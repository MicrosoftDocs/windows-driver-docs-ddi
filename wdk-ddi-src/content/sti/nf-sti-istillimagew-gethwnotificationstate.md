---
UID: NF:sti.IStillImageW.GetHwNotificationState
title: IStillImageW::GetHwNotificationState (sti.h)
description: The IStillImage::GetHwNotificationState method indicates whether applications will be notified when Still Image Device Events occur on a specified device.
old-location: image\istillimage_gethwnotificationstate.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStillImageW::GetHwNotificationState"]
ms.keywords: GetHwNotificationState, GetHwNotificationState method [Imaging Devices], GetHwNotificationState method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],GetHwNotificationState method, IStillImageW.GetHwNotificationState, IStillImageW::GetHwNotificationState, image.istillimage_gethwnotificationstate, sti/IStillImageW::GetHwNotificationState, stifnc_9dab6727-1954-4054-b918-be9666c05301.xml
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
 - IStillImageW::GetHwNotificationState
 - sti/IStillImageW::GetHwNotificationState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW::GetHwNotificationState
---

# IStillImageW::GetHwNotificationState


## -description

The <b>IStillImage::GetHwNotificationState</b> method indicates whether applications will be notified when <a href="/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> occur on a specified device.

## -parameters

### -param pwszDeviceName [in]


Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a> or <a href="/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>.

### -param pbCurrentState [out]


Receives <b>TRUE</b> if event notification is enabled, or <b>FALSE</b> otherwise.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

Before calling <b>IStillImage::GetHwNotificationState</b>, clients of the <b>IStillImage</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff543780(v=vs.85)">IStillImage::EnableHwNotifications</a>



<a href="/windows-hardware/drivers/ddi/_image/index">IStillImageW</a>

