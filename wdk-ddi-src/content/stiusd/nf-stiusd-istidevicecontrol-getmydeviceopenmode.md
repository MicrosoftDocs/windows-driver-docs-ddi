---
UID: NF:stiusd.IStiDeviceControl.GetMyDeviceOpenMode
title: IStiDeviceControl::GetMyDeviceOpenMode method
author: windows-driver-content
description: The IStiDeviceControl::GetMyDeviceOpenMode method allows a still image minidriver to obtain the transfer mode that an application specified when it created an instance of a still image device.
old-location: image\istidevicecontrol_getmydeviceopenmode.htm
old-project: image
ms.assetid: 814e739f-6147-4287-876e-db6fc41c5aa1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: stifnc_a3082d9f-d152-4494-b11f-e9d2bd1efe63.xml, IStiDeviceControl::GetMyDeviceOpenMode, GetMyDeviceOpenMode, stiusd/IStiDeviceControl::GetMyDeviceOpenMode, GetMyDeviceOpenMode method [Imaging Devices], IStiDeviceControl interface, image.istidevicecontrol_getmydeviceopenmode, IStiDeviceControl, IStiDeviceControl interface [Imaging Devices], GetMyDeviceOpenMode method, GetMyDeviceOpenMode method [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: stiusd.h
req.include-header: Stiusd.h
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
req.lib: stiusd.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	stiusd.h
apiname:
-	IStiDeviceControl.GetMyDeviceOpenMode
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiDeviceControl::GetMyDeviceOpenMode method


## -description


The <b>IStiDeviceControl::GetMyDeviceOpenMode</b> method allows a still image minidriver to obtain the transfer mode that an application specified when it created an instance of a still image device.


## -syntax


````
HRESULT GetMyDeviceOpenMode(
   LPDWORD pdwOpenMode
);
````


## -parameters




### -param pdwOpenMode

Receives the mode flag that an application previously specified as the <i>dwMode</i> argument to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a>.


## -returns


If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.



## -remarks


A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as an input argument to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff543824">IStiUSD::Initialize</a> method.


