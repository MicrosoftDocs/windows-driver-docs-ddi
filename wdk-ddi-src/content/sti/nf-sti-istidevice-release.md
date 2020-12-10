---
UID: NF:sti.IStiDevice.Release
title: IStiDevice::Release (sti.h)
description: The IStiDevice::Release method closes the instance of the COM object that was created by a previous call to IStillImage::CreateDevice, and removes access to the object's interface.
old-location: image\istidevice_release.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiDevice::Release"]
ms.keywords: IStiDevice interface [Imaging Devices],Release method, IStiDevice.Release, IStiDevice::Release, Release, Release method [Imaging Devices], Release method [Imaging Devices],IStiDevice interface, image.istidevice_release, sti/IStiDevice::Release, stifnc_70352bce-ba09-45c1-97a8-add180942d05.xml
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
 - IStiDevice::Release
 - sti/IStiDevice::Release
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Sti.h
api_name:
 - IStiDevice.Release
---

# IStiDevice::Release


## -description

The <b>IStiDevice::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a>, and removes access to the object's interface.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.
