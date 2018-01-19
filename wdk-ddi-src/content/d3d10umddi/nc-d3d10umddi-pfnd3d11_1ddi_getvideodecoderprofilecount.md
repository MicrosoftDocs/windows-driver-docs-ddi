---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT
title: PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT
author: windows-driver-content
description: Queries the number of video decoder profiles that are supported by the display miniport driver.
old-location: display\getvideodecoderprofilecount.htm
old-project: display
ms.assetid: ae24bc29-177e-48a1-adf9-ed8c79b7f39c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnGetVideoDecoderProfileCount
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT callback



## -description
Queries the number of video decoder profiles that are supported by the display miniport driver.



## -prototype

````
PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT pfnGetVideoDecoderProfileCount;

VOID APIENTRY* pfnGetVideoDecoderProfileCount(
  _In_  D3D10DDI_HDEVICE hDevice,
  _Out_ UINT             *pDecodeProfileCount
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param pDecodeProfileCount [out]

A pointer to a UINT value that specifies the maximum number of decoder profiles that are supported.


## -returns
This callback function does not return a value.


## -remarks
