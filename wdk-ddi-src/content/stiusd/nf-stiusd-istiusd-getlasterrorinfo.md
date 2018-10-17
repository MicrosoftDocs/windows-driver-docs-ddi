---
UID: NF:stiusd.IStiUSD.GetLastErrorInfo
title: IStiUSD::GetLastErrorInfo
author: windows-driver-content
description: A still image minidriver's IStiUSD::GetLastErrorInfo method returns information about the last known error associated with a still image device.
old-location: image\istiusd_getlasterrorinfo.htm
tech.root: image
ms.assetid: 0b393f55-6054-4c45-aa3d-7588139b34e5
ms.date: 5/3/2018
ms.keywords: GetLastErrorInfo, GetLastErrorInfo method [Imaging Devices], GetLastErrorInfo method [Imaging Devices],IStiUSD interface, IStiUSD interface [Imaging Devices],GetLastErrorInfo method, IStiUSD.GetLastErrorInfo, IStiUSD::GetLastErrorInfo, image.istiusd_getlasterrorinfo, stifnc_52990060-06be-455b-897b-c7f8e0bbe608.xml, stiusd/IStiUSD::GetLastErrorInfo
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	stiusd.h
api_name:
-	IStiUSD.GetLastErrorInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiUSD::GetLastErrorInfo


## -description


A still image minidriver's <b>IStiUSD::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.


## -parameters




### -param pLastErrorInfo

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548396">STI_ERROR_INFO</a> structure to receive error information.


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>Stierr.h</i>.




## -remarks



The method should fill in the received <a href="https://msdn.microsoft.com/library/windows/hardware/ff548396">STI_ERROR_INFO</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543749">IStiDevice::GetLastErrorInfo</a>



<a href="https://msdn.microsoft.com/62740263-5bbb-48e1-be3d-9ee9cb37d6b9">IStiUSD</a>
 

 

