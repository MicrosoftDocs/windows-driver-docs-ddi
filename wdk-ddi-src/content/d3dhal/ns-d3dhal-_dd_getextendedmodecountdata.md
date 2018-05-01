---
UID: NS:d3dhal._DD_GETEXTENDEDMODECOUNTDATA
title: "_DD_GETEXTENDEDMODECOUNTDATA"
author: windows-driver-content
description: DirectX 9.0 and later versions only. DD_GETEXTENDEDMODECOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODECOUNT.
old-location: display\dd_getextendedmodecountdata.htm
old-project: display
ms.assetid: 138b6ae2-4c89-40cb-a7b0-d1208e68c460
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DD_GETEXTENDEDMODECOUNTDATA, DD_GETEXTENDEDMODECOUNTDATA structure [Display Devices], _DD_GETEXTENDEDMODECOUNTDATA, d3dhal/DD_GETEXTENDEDMODECOUNTDATA, d3dstrct_2139722c-6eff-4c77-b899-2085de6239fd.xml, display.dd_getextendedmodecountdata
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	DD_GETEXTENDEDMODECOUNTDATA
product: Windows
targetos: Windows
req.typenames: DD_GETEXTENDEDMODECOUNTDATA
---

# _DD_GETEXTENDEDMODECOUNTDATA structure


## -description



   DirectX 9.0 and later versions only.
   

DD_GETEXTENDEDMODECOUNTDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODECOUNT.


## -struct-fields




### -field gdi2

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data for the query.


### -field dwModeCount

Receives the number of supported extended display modes.


### -field dwReserved

Specifies a reserved field. Driver should not read or write.


## -remarks



To handle D3DGDI2_TYPE_GETEXTENDEDMODECOUNT, the driver must store the number of extended display modes that it supports in the <b>dwModeCount</b> member of DD_GETEXTENDEDMODECOUNTDATA. Display modes are described by D3DDISPLAYMODE structures. For more information about D3DDISPLAYMODE, see the DirectX SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551559">DD_GETEXTENDEDMODEDATA</a>
 

 

