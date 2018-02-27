---
UID: NF:stiusd.IStiUSD.GetLastErrorInfo
title: IStiUSD::GetLastErrorInfo method
author: windows-driver-content
description: A still image minidriver's IStiUSD::GetLastErrorInfo method returns information about the last known error associated with a still image device.
old-location: image\istiusd_getlasterrorinfo.htm
old-project: image
ms.assetid: 0b393f55-6054-4c45-aa3d-7588139b34e5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetLastErrorInfo method [Imaging Devices], GetLastErrorInfo method [Imaging Devices], IStiUSD interface, GetLastErrorInfo,IStiUSD.GetLastErrorInfo, IStiUSD, IStiUSD interface [Imaging Devices], GetLastErrorInfo method, IStiUSD::GetLastErrorInfo, image.istiusd_getlasterrorinfo, stifnc_52990060-06be-455b-897b-c7f8e0bbe608.xml, stiusd/IStiUSD::GetLastErrorInfo
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
-	IStiUSD.GetLastErrorInfo
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiUSD::GetLastErrorInfo method


## -description


A still image minidriver's <b>IStiUSD::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.


## -syntax


````
HRESULT GetLastErrorInfo(
   STI_ERROR_INFO *pLastErrorInfo
);
````


## -parameters




### -param pLastErrorInfo

Caller-supplied pointer to an <a href="..\sti\ns-sti-_error_infow.md">STI_ERROR_INFO</a> structure to receive error information.


## -returns



If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>Stierr.h</i>.




## -remarks



The method should fill in the received <a href="..\sti\ns-sti-_error_infow.md">STI_ERROR_INFO</a> structure.




## -see-also

<a href="..\stiusd\nn-stiusd-istiusd.md">IStiUSD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543749">IStiDevice::GetLastErrorInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::GetLastErrorInfo method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

