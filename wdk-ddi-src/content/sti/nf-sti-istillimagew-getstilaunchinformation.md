---
UID: NF:sti.IStillImageW.GetSTILaunchInformation
title: IStillImageW::GetSTILaunchInformation (sti.h)
description: The IStillImage::GetSTILaunchInformation method returns the reason the calling still image application was started, if the still image event monitor started it.
old-location: image\istillimage_getstilaunchinformation.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStillImageW::GetSTILaunchInformation"]
ms.keywords: GetSTILaunchInformation, GetSTILaunchInformation method [Imaging Devices], GetSTILaunchInformation method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],GetSTILaunchInformation method, IStillImageW.GetSTILaunchInformation, IStillImageW::GetSTILaunchInformation, image.istillimage_getstilaunchinformation, sti/IStillImageW::GetSTILaunchInformation, stifnc_b73269ec-512a-4d07-a43a-8c72a28a751b.xml
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
 - IStillImageW::GetSTILaunchInformation
 - sti/IStillImageW::GetSTILaunchInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW::GetSTILaunchInformation
---

# IStillImageW::GetSTILaunchInformation


## -description

The <b>IStillImage::GetSTILaunchInformation</b> method returns the reason the calling still image application was started, if the still image event monitor started it.

## -parameters

### -param pwszDeviceName 

[out]
Caller-supplied pointer to a buffer, STI_MAX_INTERNAL_NAME_LENGTH bytes in length, to receive the internal device name of the still image device for which the application was started.

### -param pdwEventCode 

[out, optional]
Reserved for future use.

### -param pwszEventName 

[out]
Caller-supplied pointer to a buffer that is large enough to receive a string representation of a GUID. The GUID represents the <a href="/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> for which the application was started.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

If the still image event monitor started the application, the <i>pwszDeviceName</i> and <i>pwszEventName</i> values identify the <b>/StiDevice</b> and <b>/StiEvent</b> command-line arguments (see the description of <a href="/previous-versions/windows/hardware/drivers/ff543798(v=vs.85)">IStillImage::RegisterLaunchApplication</a>). If the event monitor did not start the application, the method returns STIERR_GENERIC.

Before calling <b>IStillImage::GetSTILaunchInformation</b>, clients of the <b>IStillImage</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

