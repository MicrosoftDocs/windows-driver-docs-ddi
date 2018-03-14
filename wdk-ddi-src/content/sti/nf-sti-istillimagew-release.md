---
UID: NF:sti.IStillImageW.Release
title: IStillImageW::Release method
author: windows-driver-content
description: The IStillImage::Release method closes the instance of the COM object that was created by a previous call to IStillImage::StiCreateInstance, and removes access to the object's interface.
old-location: image\istillimage_release.htm
old-project: image
ms.assetid: 3c595531-a1b0-48a5-867c-f1e6558e46ff
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IStillImageW, IStillImageW interface [Imaging Devices], Release method, IStillImageW::Release, Release method [Imaging Devices], Release method [Imaging Devices], IStillImageW interface, Release,IStillImageW.Release, image.istillimage_release, sti/IStillImageW::Release, stifnc_e1ab4835-ed24-4c92-a879-f57061656825.xml
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Sti.h
api_name:
-	IStillImageW.Release
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::Release method


## -description


The <b>IStillImage::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a>, and removes access to the object's interface.


## -syntax


````
HRESULT Release();
````


## -parameters






## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



Before calling <b>IStillImage::Release</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.



