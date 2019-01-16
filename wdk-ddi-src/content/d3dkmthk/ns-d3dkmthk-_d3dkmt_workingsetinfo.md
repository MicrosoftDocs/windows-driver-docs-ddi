---
UID: NS:d3dkmthk._D3DKMT_WORKINGSETINFO
title: "_D3DKMT_WORKINGSETINFO"
description: The D3DKMT_WORKINGSETINFO structure describes information about the graphics adapter's working set that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_workingsetinfo.htm
ms.assetid: 1a5b75e4-abdd-4916-b2b5-4dbb53a525ae
ms.date: 05/10/2018
ms.keywords: D3DKMT_WORKINGSETINFO, D3DKMT_WORKINGSETINFO structure [Display Devices], OpenGL_Structs_a3992911-10eb-48fe-a755-fe14e68fbaa8.xml, _D3DKMT_WORKINGSETINFO, d3dkmthk/D3DKMT_WORKINGSETINFO, display.d3dkmt_workingsetinfo
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
-	D3DKMT_WORKINGSETINFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_WORKINGSETINFO
---

# _D3DKMT_WORKINGSETINFO structure


## -description


The D3DKMT_WORKINGSETINFO structure describes information about the graphics adapter's working set that the OpenGL installable client driver (ICD) obtains by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a> function.


## -struct-fields




### -field Flags

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff548448">D3DKMT_WORKINGSETFLAGS</a> structure that indicates, in bit-field flags, working-set properties.


### -field MinimumWorkingSetPercentile

[out] The minimum working-set percentile. 


### -field MaximumWorkingSetPercentile

[out] The maximum working-set percentile. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548203">D3DKMT_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548448">D3DKMT_WORKINGSETFLAGS</a>
 

 

