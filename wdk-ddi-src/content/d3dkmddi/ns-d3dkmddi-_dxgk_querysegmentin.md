---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTIN
title: _DXGK_QUERYSEGMENTIN (d3dkmddi.h)
description: The DXGK_QUERYSEGMENTIN structure describes relevant information for a memory-segment query through a call to the display miniport driver's DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentin.htm
ms.assetid: 5a3e6edf-40c7-49f3-8394-0e54c080c92c
ms.date: 05/10/2018
ms.keywords: DXGK_QUERYSEGMENTIN, DXGK_QUERYSEGMENTIN structure [Display Devices], DmStructs_d47cf13d-48ec-49fd-b80c-4df1501db329.xml, _DXGK_QUERYSEGMENTIN, d3dkmddi/DXGK_QUERYSEGMENTIN, display.dxgk_querysegmentin
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DXGK_QUERYSEGMENTIN
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYSEGMENTIN
---

# _DXGK_QUERYSEGMENTIN structure


## -description


The DXGK_QUERYSEGMENTIN structure describes relevant information for a memory-segment query through a call to the display miniport driver's <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function. 


## -struct-fields




### -field AgpApertureBase

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the base address of the AGP aperture. 


### -field AgpApertureSize

[in] A LARGE_INTEGER that indicates the size, in bytes, of the available AGP aperture.


### -field AgpFlags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562039">DXGK_SEGMENTFLAGS</a> structure that identifies properties for the available AGP aperture in bit-field flags.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562018">DXGK_QUERYSEGMENTOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562035">DXGK_SEGMENTDESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562039">DXGK_SEGMENTFLAGS</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>
 

 

