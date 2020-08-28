---
UID: NF:sti.IStillImageW.Release
title: IStillImageW::Release (sti.h)
description: The IStillImage::Release method closes the instance of the COM object that was created by a previous call to IStillImage::StiCreateInstance, and removes access to the object's interface.
old-location: image\istillimage_release.htm
tech.root: image
ms.assetid: 3c595531-a1b0-48a5-867c-f1e6558e46ff
ms.date: 05/03/2018
keywords: ["IStillImageW::Release"]
ms.keywords: IStillImageW interface [Imaging Devices],Release method, IStillImageW.Release, IStillImageW::Release, Release, Release method [Imaging Devices], Release method [Imaging Devices],IStillImageW interface, image.istillimage_release, sti/IStillImageW::Release, stifnc_e1ab4835-ed24-4c92-a879-f57061656825.xml
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
 - IStillImageW::Release
 - sti/IStillImageW::Release
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Sti.h
api_name:
 - IStillImageW.Release
---

# IStillImageW::Release


## -description

The <b>IStillImage::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a>, and removes access to the object's interface.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

Before calling <b>IStillImage::Release</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

