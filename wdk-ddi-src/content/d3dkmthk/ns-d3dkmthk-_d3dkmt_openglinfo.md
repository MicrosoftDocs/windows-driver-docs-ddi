---
UID: NS:d3dkmthk._D3DKMT_OPENGLINFO
title: "_D3DKMT_OPENGLINFO"
author: windows-driver-content
description: The D3DKMT_OPENGLINFO structure describes OpenGL installable client driver (ICD) information.
old-location: display\d3dkmt_openglinfo.htm
old-project: display
ms.assetid: d8e571dd-b823-4cad-96b6-c7841a1234c4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_OPENGLINFO, D3DKMT_OPENGLINFO structure [Display Devices], OpenGL_Structs_93ba7fd7-969f-4edf-a6ce-38a135bcda83.xml, _D3DKMT_OPENGLINFO, d3dkmthk/D3DKMT_OPENGLINFO, display.d3dkmt_openglinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_OPENGLINFO
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_OPENGLINFO
---

# _D3DKMT_OPENGLINFO structure


## -description


The D3DKMT_OPENGLINFO structure describes OpenGL installable client driver (ICD) information.


## -struct-fields




### -field UmdOpenGlIcdFileName

[out] An array of wide characters that contains the file name of the OpenGL ICD.


### -field Version

[out] The version of the OpenGL ICD.


### -field Flags

[in] This member is currently unused.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548203">D3DKMT_QUERYADAPTERINFO</a>
 

 

