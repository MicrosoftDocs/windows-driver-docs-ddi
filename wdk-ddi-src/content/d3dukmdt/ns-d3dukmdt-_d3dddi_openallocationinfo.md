---
UID: NS:d3dukmdt._D3DDDI_OPENALLOCATIONINFO
title: "_D3DDDI_OPENALLOCATIONINFO"
author: windows-driver-content
description: The D3DDDI_OPENALLOCATIONINFO structure describes an allocation to be opened.
old-location: display\d3dddi_openallocationinfo.htm
old-project: display
ms.assetid: cd50602a-c4aa-410b-9ed6-56d7237571cd
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3DDDI_OPENALLOCATIONINFO structure [Display Devices], _D3DDDI_OPENALLOCATIONINFO, D3DDDI_OPENALLOCATIONINFO, display.d3dddi_openallocationinfo, d3dukmdt/D3DDDI_OPENALLOCATIONINFO, D3D_other_Structs_cfb185b4-cc7d-4c1a-9e76-6032816feab0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDI_OPENALLOCATIONINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_OPENALLOCATIONINFO
---

# _D3DDDI_OPENALLOCATIONINFO structure


## -description


The D3DDDI_OPENALLOCATIONINFO structure describes an allocation to be opened.


## -syntax


````
typedef struct _D3DDDI_OPENALLOCATIONINFO {
  D3DKMT_HANDLE hAllocation;
  const VOID    *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3DDDI_OPENALLOCATIONINFO;
````


## -struct-fields




### -field hAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation. The user-mode display driver should use this handle to reference the allocation in the command buffer.


### -field pPrivateDriverData

[in] A pointer to a block of private data, which was passed to the display miniport driver when the resource was created. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that is pointed to by <b>pPrivateDriverData</b>.

