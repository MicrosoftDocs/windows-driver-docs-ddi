---
UID: NS:d3dukmdt._D3DDDI_KERNELOVERLAYINFO
title: "_D3DDDI_KERNELOVERLAYINFO"
author: windows-driver-content
description: The D3DDDI_KERNELOVERLAYINFO structure describes information for a kernel-mode overlay object.
old-location: display\d3dddi_kerneloverlayinfo.htm
old-project: display
ms.assetid: 0a9685f8-f201-4d1b-aef6-c4ac78100a80
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_KERNELOVERLAYINFO, D3DDDI_KERNELOVERLAYINFO structure [Display Devices], D3D_other_Structs_ee8ebc87-60be-4b70-8428-4db20bcbdaa0.xml, _D3DDDI_KERNELOVERLAYINFO, d3dukmdt/D3DDDI_KERNELOVERLAYINFO, display.d3dddi_kerneloverlayinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dukmdt.h
api_name:
-	D3DDDI_KERNELOVERLAYINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_KERNELOVERLAYINFO
---

# _D3DDDI_KERNELOVERLAYINFO structure


## -description


The D3DDDI_KERNELOVERLAYINFO structure describes information for a kernel-mode overlay object.


## -syntax


````
typedef struct _D3DDDI_KERNELOVERLAYINFO {
  D3DKMT_HANDLE hAllocation;
  D3DDDIRECT    DstRect;
  D3DDDIRECT    SrcRect;
  VOID          *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3DDDI_KERNELOVERLAYINFO;
````


## -struct-fields




### -field hAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation to be displayed.


### -field DstRect

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddirect.md">D3DDDIRECT</a> structure that contains the overlay destination rectangle in device coordinates.


### -field SrcRect

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddirect.md">D3DDDIRECT</a> structure that contains the overlay source rectangle in device coordinates.


### -field pPrivateDriverData

[in] A pointer to a block of private data, which is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that is pointed to by <b>pPrivateDriverData</b>.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddirect.md">D3DDDIRECT</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>



 

 


