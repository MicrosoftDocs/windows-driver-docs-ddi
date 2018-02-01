---
UID: NF:stiusd.IStiDeviceControl.GetMyDeviceHandle
title: IStiDeviceControl::GetMyDeviceHandle method
author: windows-driver-content
description: This topic describes the GetMyDeviceHandle method.
old-location: image\istidevicecontrol_getmydevicehandle.htm
old-project: image
ms.assetid: B20B2AE6-A408-451C-B46D-803139E8B57F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetMyDeviceHandle method [Imaging Devices], IStiDeviceControl interface, IStiDeviceControl::GetMyDeviceHandle, image.istidevicecontrol_getmydevicehandle, GetMyDeviceHandle method [Imaging Devices], IStiDeviceControl, GetMyDeviceHandle, IStiDeviceControl interface [Imaging Devices], GetMyDeviceHandle method, stiusd/IStiDeviceControl::GetMyDeviceHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: stiusd.h
req.include-header: 
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
req.lib: stiusd.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Stiusd.h
apiname:
-	IStiDeviceControl.GetMyDeviceHandle
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiDeviceControl::GetMyDeviceHandle method


## -description


This topic describes the <b>GetMyDeviceHandle</b> method.


## -syntax


````
HRESULT GetMyDeviceHandle(
   LPHANDLE lph
);
````


## -parameters




### -param lph

Defines the <b>LPHANDLE</b> parameter <i>lph</i>.


## -returns


Defines the <b>HRESULT</b> return value.



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/image/istidevicecontrol-com-interface">IStiDeviceControl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDeviceControl::GetMyDeviceHandle method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

