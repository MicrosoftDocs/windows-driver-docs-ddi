---
UID: NS:d3dhal._DD_GETFORMATCOUNTDATA
title: _DD_GETFORMATCOUNTDATA (d3dhal.h)
description: DirectX 8.0 and later versions only. DD_GETFORMATCOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMATCOUNT.
old-location: display\dd_getformatcountdata.htm
tech.root: display
ms.assetid: 5f334f48-a262-4b09-98c4-766039de3f0e
ms.date: 05/10/2018
keywords: ["_DD_GETFORMATCOUNTDATA structure"]
ms.keywords: DD_GETFORMATCOUNTDATA, DD_GETFORMATCOUNTDATA structure [Display Devices], _DD_GETFORMATCOUNTDATA, d3dhal/DD_GETFORMATCOUNTDATA, d3dstrct_610983cc-4f8a-4c16-b60b-960dbf0c58e9.xml, display.dd_getformatcountdata
f1_keywords:
 - "d3dhal/DD_GETFORMATCOUNTDATA"
 - "DD_GETFORMATCOUNTDATA"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- DD_GETFORMATCOUNTDATA
targetos: Windows
req.typenames: DD_GETFORMATCOUNTDATA
---

# _DD_GETFORMATCOUNTDATA structure


## -description



   DirectX 8.0 and later versions only.
   

DD_GETFORMATCOUNTDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMATCOUNT.


## -struct-fields




### -field gdi2

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwFormatCount

Receives the number of supported surface formats.


### -field dwReserved

<b>DirectX 8.0 and 8.1 versions only.</b> Specifies a reserved field. Driver should not read or write.

<b>DirectX 9.0 and later versions only.</b> Specifies the version of the DirectX runtime being used by the application. This member is set to DD_RUNTIME_VERSION, which is 0x00000900 for DirectX 9.0.


## -remarks



To handle the D3DGDI2_TYPE_GETFORMATCOUNT request, the driver must store the number of DirectX 8.0 and later DDI style surface formats that it supports in the <b>dwFormatCount</b> member of DD_GETFORMATCOUNTDATA. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/the-texture-format-list">The Texture Format List</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a>



<a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>
 

 

