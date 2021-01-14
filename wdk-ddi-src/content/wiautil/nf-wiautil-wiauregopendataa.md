---
UID: NF:wiautil.wiauRegOpenDataA
title: wiauRegOpenDataA function (wiautil.h)
description: The wiauRegOpenData function opens the DeviceData registry key.
old-location: image\wiauregopendata.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiauRegOpenDataA function"]
ms.keywords: image.wiauregopendata, wiauFncs_1718e270-b13c-4325-bb4a-a872becaa8bb.xml, wiauRegOpenData, wiauRegOpenData function [Imaging Devices], wiauRegOpenDataA, wiauRegOpenDataW, wiautil/wiauRegOpenData
req.header: wiautil.h
req.include-header: Wiautil.h
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
 - wiauRegOpenDataA
 - wiautil/wiauRegOpenDataA
 - wiauRegOpenData
 - wiautil/wiauRegOpenData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiautil.h
api_name:
 - wiauRegOpenData
---

# wiauRegOpenDataA function


## -description

The <b>wiauRegOpenData</b> function opens the <b>DeviceData</b> registry key.

## -parameters

### -param hkeyAncestor 

[in]
Specifies the key handle of the parent. This parameter should be set to the value used in the call to the <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a> method.

### -param phkeyDeviceData 

[in, out]
Pointer to a memory location that receives the opened key handle.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error.

## -remarks

Call this function only in the STI <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a> method. Call <b>RegCloseKey</b> (described in the Microsoft Windows SDK documentation) when you are finished with the registry.

## -see-also

<a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a>

