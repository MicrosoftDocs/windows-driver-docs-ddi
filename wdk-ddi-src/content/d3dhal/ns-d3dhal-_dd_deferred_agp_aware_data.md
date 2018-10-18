---
UID: NS:d3dhal._DD_DEFERRED_AGP_AWARE_DATA
title: "_DD_DEFERRED_AGP_AWARE_DATA"
author: windows-driver-content
description: DirectX 8.0 and later versions and NT-based operating systems only. DD_DEFERRED_AGP_AWARE_DATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for D3DGDI2_TYPE_DEFERRED_AGP_AWARE notifications.
old-location: display\dd_deferred_agp_aware_data.htm
tech.root: display
ms.assetid: df36008a-2ee4-4e3e-8bad-7da1f27a695d
ms.date: 5/10/2018
ms.keywords: DD_DEFERRED_AGP_AWARE_DATA, DD_DEFERRED_AGP_AWARE_DATA structure [Display Devices], _DD_DEFERRED_AGP_AWARE_DATA, d3dhal/DD_DEFERRED_AGP_AWARE_DATA, d3dstrct_f07b3180-3442-4c3f-974b-eaf58a3a03df.xml, display.dd_deferred_agp_aware_data
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	DD_DEFERRED_AGP_AWARE_DATA
product:
- Windows
targetos: Windows
req.typenames: DD_DEFERRED_AGP_AWARE_DATA
---

# _DD_DEFERRED_AGP_AWARE_DATA structure


## -description



   DirectX 8.0 and later versions and NT-based operating systems only.
   

DD_DEFERRED_AGP_AWARE_DATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for D3DGDI2_TYPE_DEFERRED_AGP_AWARE notifications.


## -struct-fields




### -field gdi2

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


## -remarks



Whenever a display device is created, the driver receives a <b>GetDriverInfo2</b> call with D3DGDI2_TYPE_DEFERRED_AGP_AWARE type and can determine if it should disable its other mechanisms that handle AGP memory and instead use the D3DGDI2_TYPE_FREE_DEFERRED_AGP and D3DGDI2_TYPE_DEFER_AGP_FREES notifications that the runtime subsequently sends.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>
 

 

