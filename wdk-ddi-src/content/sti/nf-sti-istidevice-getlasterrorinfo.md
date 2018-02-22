---
UID: NF:sti.IStiDevice.GetLastErrorInfo
title: IStiDevice::GetLastErrorInfo method
author: windows-driver-content
description: The IStiDevice::GetLastErrorInfo method returns information about the last known error associated with a still image device.
old-location: image\istidevice_getlasterrorinfo.htm
old-project: Image
ms.assetid: de2f8897-c75f-4c37-aecb-f36d0f9933f9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: stifnc_f54b574c-5894-4029-888c-fe60738858d7.xml, GetLastErrorInfo, image.istidevice_getlasterrorinfo, IStiDevice, GetLastErrorInfo method [Imaging Devices], IStiDevice interface [Imaging Devices], GetLastErrorInfo method, sti/IStiDevice::GetLastErrorInfo, GetLastErrorInfo method [Imaging Devices], IStiDevice interface, IStiDevice::GetLastErrorInfo
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
-	IStiDevice.GetLastErrorInfo
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::GetLastErrorInfo method


## -description


The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.


## -syntax


````
HRESULT GetLastErrorInfo(
  [out] STI_ERROR_INFO *pLastErrorInf
);
````


## -parameters




### -param pLastErrorInfo






#### - pLastErrorInf [out]

Caller-supplied pointer to an <a href="..\sti\ns-sti-_error_infow.md">STI_ERROR_INFO</a> structure to receive error information.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the most recent error by filling in the caller-supplied <a href="..\sti\ns-sti-_error_infow.md">STI_ERROR_INFO</a> structure. The method calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543820">IStiUSD::GetLastErrorInfo</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::GetLastErrorInfo</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.



