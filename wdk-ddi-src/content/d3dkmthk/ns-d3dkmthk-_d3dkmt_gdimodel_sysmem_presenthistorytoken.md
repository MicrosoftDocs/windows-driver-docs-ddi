---
UID: NS:d3dkmthk._D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN
title: _D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN (d3dkmthk.h)
description: The D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure identifies a GDI system present-history operation.
old-location: display\d3dkmt_gdimodel_sysmem_presenthistorytoken.htm
ms.assetid: 764e6504-a056-44c4-acf5-1788832a9c70
ms.date: 05/10/2018
keywords: ["_D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure"]
ms.keywords: D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN, D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_2e7ec746-9d7b-43b8-8606-1c92481031a3.xml, _D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN, display.d3dkmt_gdimodel_sysmem_presenthistorytoken
f1_keywords:
 - "d3dkmthk/D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN"
 - "D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
- d3dkmthk.h
api_name:
- D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN
---

# _D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure


## -description


The D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure identifies a GDI system present-history operation.


## -struct-fields




### -field hlsurf

[in] A 64-bit value that specifies the handle to a logical surface to copy from. 


### -field dwDirtyFlags

[in] A set of flags in a 32-bit value that identifies the active rectangles (dirty regions) of the GDI surface. 


### -field uiCookie

[in] A 64-bit value that specifies the handle to a physical surface to copy to. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_presenthistorytoken">D3DKMT_PRESENTHISTORYTOKEN</a>
 

 

