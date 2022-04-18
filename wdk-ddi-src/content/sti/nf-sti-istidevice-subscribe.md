---
UID: NF:sti.IStiDevice.Subscribe
title: IStiDevice::Subscribe (sti.h)
description: The IStiDevice::Subscribe method registers the caller to receive notifications of device events.
tech.root: image
ms.date: 04/18/2022
keywords: ["IStiDevice::Subscribe"]
ms.keywords: IStiDevice interface [Imaging Devices],Subscribe method, IStiDevice.Subscribe, IStiDevice::Subscribe, Subscribe, Subscribe method [Imaging Devices], Subscribe method [Imaging Devices],IStiDevice interface, image.istidevice_subscribe, sti/IStiDevice::Subscribe, stifnc_2c707880-5ace-4a2e-813e-1ee304cea41f.xml
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
 - IStiDevice::Subscribe
 - sti/IStiDevice::Subscribe
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice::Subscribe
---

## -description

The **IStiDevice::Subscribe** method registers the caller to receive notifications of device events.

## -parameters

### -param lpSubsribe [in, out]

Caller-supplied pointer to an [STISUBSCRIBE](/windows-hardware/drivers/ddi/sti/ns-sti-_stisubscribe) structure containing subscription parameter values.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

The **IStiDevice::Subscribe** method is typically called by applications that intercept events from devices and reroute them. The method allows these applications to be notified of [Still Image Device Events](/windows-hardware/drivers/image/still-image-device-events) so they can then dispatch control to appropriate display applications.

Based on contents supplied in the [STISUBSCRIBE](/windows-hardware/drivers/ddi/sti/ns-sti-_stisubscribe) structure, the caller can request to be notified of device events by Windows messages or by Win32 events (by means of **SetEvent** calls).

When the application receives notification of an event, it can call [IStiDevice::GetLastNotificationData](/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-getlastnotificationdata) to find out which event occurred.

Before calling **IStiDevice::Subscribe**, clients of the **IStiDevice** COM interface must call [IStillImage::CreateDevice](/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)) to obtain an **IStiDevice** interface pointer, which provides access to a specified device.

## -see-also

[IStiDevice](/windows-hardware/drivers/ddi/_image/index)

[IStiDevice::UnSubscribe](/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unsubscribe)

[IStillImage::LaunchApplicationForDevice](/previous-versions/windows/hardware/drivers/ff543796(v=vs.85))
