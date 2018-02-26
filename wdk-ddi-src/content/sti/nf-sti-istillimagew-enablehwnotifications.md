---
UID: NF:sti.IStillImageW.EnableHwNotifications
title: IStillImageW::EnableHwNotifications method
author: windows-driver-content
description: The IStillImage::EnableHwNotifications method requests the still image event monitor to enable or disable the notification of applications when Still Image Device Events occur for a specified device.
old-location: image\istillimage_enablehwnotifications.htm
old-project: image
ms.assetid: 54b4468a-7823-4afe-8845-696c4a534367
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, E, EnableHwNotifications method [Imaging Devices], EnableHwNotifications method [Imaging Devices], IStillImageW interface, EnableHwNotifications,IStillImageW.EnableHwNotifications, H, I, IStillImageW, IStillImageW interface [Imaging Devices], EnableHwNotifications method, IStillImageW::EnableHwNotifications, N, S, W, a, b, c, e, f, g, i, image.istillimage_enablehwnotifications, l, m, n, o, s, sti/IStillImageW::EnableHwNotifications, stifnc_50df840a-7fa2-4235-864f-dee8ce5ce849.xml, t, w"
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	sti.h
apiname:
-	IStillImageW.EnableHwNotifications
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::EnableHwNotifications method


## -description


The <b>IStillImage::EnableHwNotifications</b> method requests the still image event monitor to enable or disable the notification of applications when <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a> occur for a specified device.


## -syntax


````
HRESULT EnableHwNotifications(
  [in] LPCWSTR pwszDeviceName,
       BOOL    bNewState
);
````


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.


### -param bNewState

Caller-supplied value, set to <b>TRUE</b> to enable notifications and <b>FALSE</b> to disable them.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStillImage::EnableHwNotifications</b> method enables or disables notifications of still image device events for <i>all</i> applications, not just for the calling application. Event notifications are enabled by default. This method is meant for use by applications that intercept events from devices and reroute them.

Before calling <b>IStillImage::EnableHwNotifications</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.




## -see-also

<a href="..\sti\nn-sti-istillimagew.md">IStillImageW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543796">IStillImage::LaunchApplicationForDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStillImageW::EnableHwNotifications method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

