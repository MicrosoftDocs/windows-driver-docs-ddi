---
UID: NS:d3dkmddi._DXGKARG_CREATEPROCESS
title: "_DXGKARG_CREATEPROCESS"
author: windows-driver-content
description: DXGKARG_CREATEPROCESS is used with DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.
old-location: display\dxgkarg_createprocess.htm
old-project: display
ms.assetid: F4FDF254-1C36-43DC-B1FD-376AD7658E61
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*INOUT_PDXGKARG_CREATEPROCESS, DXGKARG_CREATEPROCESS, DXGKARG_CREATEPROCESS structure [Display Devices], _DXGKARG_CREATEPROCESS, d3dkmddi/DXGKARG_CREATEPROCESS, display.dxgkarg_createprocess"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_CREATEPROCESS
product: Windows
targetos: Windows
req.typenames: DXGKARG_CREATEPROCESS
---

# _DXGKARG_CREATEPROCESS structure


## -description


<b>DXGKARG_CREATEPROCESS</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a> to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.


## -syntax


````
typedef struct _DXGKARG_CREATEPROCESS {
  HANDLE                  hDxgkProcess;
  HANDLE                  hKmdProcess;
  DXGK_CREATEPROCESSFLAGS Flags;
  UINT                    NumPasid;
  ULONG*                  pPasid;
} DXGKARG_CREATEPROCESS;
````


## -struct-fields




### -field hDxgkProcess

[in] The handle to the DirectX graphics kernel process.


### -field hKmdProcess

[out] The handle to the kernel mode driver process.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createprocessflags.md">DXGK_CREATEPROCESSFLAGS</a> structure describing the operation.


### -field NumPasid

[in] The number of elements in the process address space identifier array located in the <b>pPasid</b>  member. 


### -field pPasid

[in] A pointer to an array of process address identifiers. There will be one for each physical GPUs.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createprocessflags.md">DXGK_CREATEPROCESSFLAGS</a>



 

 


