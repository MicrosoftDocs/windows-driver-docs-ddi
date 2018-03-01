---
UID: NS:d3dkmthk._D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
title: "_D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure identifies a GDI present-history operation.
old-location: display\d3dkmt_gdimodel_presenthistorytoken.htm
old-project: display
ms.assetid: 4f602b68-7170-4e76-8875-0a0c0634caa2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN, D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_02351828-bca4-4a37-bb61-57224a125ee5.xml, _D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN, display.d3dkmt_gdimodel_presenthistorytoken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
---

# _D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure


## -description


The D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure identifies a GDI present-history operation.


## -syntax


````
typedef struct _D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN {
  ULONG64             hLogicalSurface;
  ULONG64             hPhysicalSurface;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  RECT                ScrollRect;
  POINT               ScrollOffset;
#endif 
  D3DKMT_DIRTYREGIONS DirtyRegions;
} D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN;
````


## -struct-fields




### -field hLogicalSurface

[in] A 64-bit value that specifies the handle to a logical surface to copy from. 


### -field hPhysicalSurface

[in] A 64-bit value that specifies the handle to a physical surface to copy to. 


### -field ScrollRect

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field ScrollOffset

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DirtyRegions

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dirtyregions.md">D3DKMT_DIRTYREGIONS</a> structure that identifies the active rectangles (dirty regions) of the GDI surface. 


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dirtyregions.md">D3DKMT_DIRTYREGIONS</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

