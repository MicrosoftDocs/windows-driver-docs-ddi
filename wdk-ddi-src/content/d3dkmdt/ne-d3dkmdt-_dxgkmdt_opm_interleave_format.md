---
UID: NE:d3dkmdt._DXGKMDT_OPM_INTERLEAVE_FORMAT
title: "_DXGKMDT_OPM_INTERLEAVE_FORMAT"
author: windows-driver-content
description: The DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration indicates the scan line ordering of a video frame from a protected output's signal.
old-location: display\dxgkmdt_opm_interleave_format.htm
old-project: display
ms.assetid: beaee817-5a91-40df-8b29-4750e3c1600e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, D, DXGKMDT_OPM_INTERLEAVE_FORMAT, DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration [Display Devices], DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG, DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST, DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST, DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER, DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE, DmEnums_7b247abd-613b-495b-aea0-d53d9b519525.xml, E, F, G, I, K, L, M, N, O, P, R, T, V, X, _, _DXGKMDT_OPM_INTERLEAVE_FORMAT, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE, display.dxgkmdt_opm_interleave_format"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_INTERLEAVE_FORMAT
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_INTERLEAVE_FORMAT
---

# _DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration


## -description


The DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration indicates the scan line ordering of a video frame from a protected output's signal. 


## -syntax


````
typedef enum _DXGKMDT_OPM_INTERLEAVE_FORMAT { 
  DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER                   = 0,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE             = 2,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST  = 3,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST   = 4,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG             = 0xFFFFFFFF
} DXGKMDT_OPM_INTERLEAVE_FORMAT;
````


## -enum-fields




### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER

Indicates that the video frame has a scan line ordering other than those given in the following constants of this enumeration.


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE

Indicates that each video frame has a scan line ordering that is progressive (that is, not interlaced).


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST

Indicates that each video frame has a scan line ordering that is interlaced, each field contains half of a frame, and the even scan lines are displayed first. 


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST

Indicates that each video frame has a scan line ordering that is interlaced, each field contains half of a frame, and the odd scan lines are displayed first. 


### -field DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.


## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

