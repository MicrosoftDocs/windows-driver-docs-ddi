---
UID: NF:stiusd.IStiUSD.GetLastErrorInfo
title: IStiUSD::GetLastErrorInfo (stiusd.h)
description: A still image minidriver's IStiUSD::GetLastErrorInfo method returns information about the last known error associated with a still image device.
old-location: image\istiusd_getlasterrorinfo.htm
tech.root: image
ms.assetid: 0b393f55-6054-4c45-aa3d-7588139b34e5
ms.date: 05/03/2018
keywords: ["IStiUSD::GetLastErrorInfo"]
ms.keywords: GetLastErrorInfo, GetLastErrorInfo method [Imaging Devices], GetLastErrorInfo method [Imaging Devices],IStiUSD interface, IStiUSD interface [Imaging Devices],GetLastErrorInfo method, IStiUSD.GetLastErrorInfo, IStiUSD::GetLastErrorInfo, image.istiusd_getlasterrorinfo, stifnc_52990060-06be-455b-897b-c7f8e0bbe608.xml, stiusd/IStiUSD::GetLastErrorInfo
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IStiUSD::GetLastErrorInfo
 - stiusd/IStiUSD::GetLastErrorInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD.GetLastErrorInfo
---

# IStiUSD::GetLastErrorInfo


## -description

A still image minidriver's <b>IStiUSD::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.

## -parameters

### -param pLastErrorInfo

Caller-supplied pointer to an <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_error_infow">STI_ERROR_INFO</a> structure to receive error information.

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>Stierr.h</i>.

## -remarks

The method should fill in the received <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_error_infow">STI_ERROR_INFO</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-getlasterrorinfo">IStiDevice::GetLastErrorInfo</a>



<a href="/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>