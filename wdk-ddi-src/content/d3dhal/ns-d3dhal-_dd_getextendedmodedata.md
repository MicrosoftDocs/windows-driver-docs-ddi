---
UID: NS:d3dhal._DD_GETEXTENDEDMODEDATA
title: _DD_GETEXTENDEDMODEDATA (d3dhal.h)
description: DirectX 9.0 and later versions only. DD_GETEXTENDEDMODEDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODE.
old-location: display\dd_getextendedmodedata.htm
tech.root: display
ms.assetid: 50b2a1fd-4214-4ad8-b087-f48c14dbe587
ms.date: 05/10/2018
ms.keywords: DD_GETEXTENDEDMODEDATA, DD_GETEXTENDEDMODEDATA structure [Display Devices], _DD_GETEXTENDEDMODEDATA, d3dhal/DD_GETEXTENDEDMODEDATA, d3dstrct_a39e1e5a-9b07-48eb-a7c6-40bcac8a21d6.xml, display.dd_getextendedmodedata
ms.topic: struct
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
- DD_GETEXTENDEDMODEDATA
product:
- Windows
targetos: Windows
req.typenames: DD_GETEXTENDEDMODEDATA
---

# _DD_GETEXTENDEDMODEDATA structure


## -description



   DirectX 9.0 and later versions only.
   

DD_GETEXTENDEDMODEDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODE.


## -struct-fields




### -field gdi2

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwModeIndex

Specifies the index of the display mode to return.


### -field mode

Receives a D3DDISPLAYMODE structure that specifies the actual display mode.


## -remarks



The runtime identifies the display mode to be returned with an integer index whose value varies between zero and one less than the number of supported display modes that were reported earlier by the driver in a DD_GETDRIVERINFO2DATA query with the type D3DGDI2_TYPE_GETEXTENDEDMODECOUNT. How these indices are mapped to actual display modes is left to the driver. However, each index must map uniquely to one supported display mode. The order in which the display modes are reported is not significant. 

When processing this <b>GetDriverInfo2</b> request the driver should read the value in the <b>dwModeIndex</b> member and map that value to one of the supported display modes (probably by using the value in <b>dwModeIndex</b> as an index into an array of D3DDISPLAYMODE structures). The driver should then copy that display mode into the <b>mode</b> member. The runtime guarantees that it only passes an index to the driver that is in the range zero to one less than the number of display modes reported by the driver. The range of the index should be validated in the debug driver build.

For more information about D3DDISPLAYMODE, see the DirectX SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getextendedmodecountdata">DD_GETEXTENDEDMODECOUNTDATA</a>
 

 

