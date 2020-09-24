---
UID: NS:sti._STINOTIFY
title: _STINOTIFY (sti.h)
description: The STINOTIFY structure is used as a parameter to the IStillImage::LaunchApplicationForDevice, IStiDevice::GetLastNotificationData, and IStiUSD::GetNotificationData methods.
old-location: image\stinotify.htm
tech.root: image
ms.assetid: 7dc42f9a-2e55-4ae5-a951-7d1d3b14564b
ms.date: 05/03/2018
keywords: ["STINOTIFY structure"]
ms.keywords: "*LPSTINOTIFY, LPSTINOTIFY, LPSTINOTIFY structure pointer [Imaging Devices], STINOTIFY, STINOTIFY structure [Imaging Devices], _STINOTIFY, image.stinotify, sti/LPSTINOTIFY, sti/STINOTIFY, stifnc_2cee63fa-a7a5-4a15-be83-e536a504bcb7.xml"
req.header: sti.h
req.include-header: Sti.h
req.target-type: Windows
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
req.typenames: STINOTIFY, *LPSTINOTIFY
f1_keywords:
 - _STINOTIFY
 - sti/_STINOTIFY
 - LPSTINOTIFY
 - sti/LPSTINOTIFY
 - STINOTIFY
 - sti/STINOTIFY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sti.h
api_name:
 - STINOTIFY
---

# _STINOTIFY structure


## -description

The STINOTIFY structure is used as a parameter to the <a href="/previous-versions/windows/hardware/drivers/ff543796(v=vs.85)">IStillImage::LaunchApplicationForDevice</a>, <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-getlastnotificationdata">IStiDevice::GetLastNotificationData</a>, and <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-getnotificationdata">IStiUSD::GetNotificationData</a> methods.

## -struct-fields

### -field dwSize

Caller-supplied size, in bytes, of the STINOTIFY structure.

### -field guidNotificationCode

GUID of the event. For more information, see <a href="/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a>.

### -field abNotificationData

Byte array containing optional, vendor-defined information.