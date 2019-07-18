---
UID: NF:sti.IStillImageW.GetHwNotificationState
title: IStillImageW::GetHwNotificationState (sti.h)
description: The IStillImage::GetHwNotificationState method indicates whether applications will be notified when Still Image Device Events occur on a specified device.
old-location: image\istillimage_gethwnotificationstate.htm
tech.root: image
ms.assetid: 8c97c4f0-3cb8-4457-8389-02d9fba51400
ms.date: 05/03/2018
ms.keywords: GetHwNotificationState, GetHwNotificationState method [Imaging Devices], GetHwNotificationState method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],GetHwNotificationState method, IStillImageW.GetHwNotificationState, IStillImageW::GetHwNotificationState, image.istillimage_gethwnotificationstate, sti/IStillImageW::GetHwNotificationState, stifnc_9dab6727-1954-4054-b918-be9666c05301.xml
ms.topic: method
f1_keywords:
 - "sti/IStillImageW.GetHwNotificationState"
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
- IStillImageW.GetHwNotificationState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::GetHwNotificationState


## -description


The <b>IStillImage::GetHwNotificationState</b> method indicates whether applications will be notified when <a href="https://docs.microsoft.com/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> occur on a specified device.


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a> or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>.


### -param pbCurrentState [out]

Receives <b>TRUE</b> if event notification is enabled, or <b>FALSE</b> otherwise.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



Before calling <b>IStillImage::GetHwNotificationState</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543780(v=vs.85)">IStillImage::EnableHwNotifications</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">IStillImageW</a>
 

 

