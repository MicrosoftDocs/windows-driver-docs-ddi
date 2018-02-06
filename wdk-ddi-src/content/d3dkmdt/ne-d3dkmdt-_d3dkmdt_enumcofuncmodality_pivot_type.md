---
UID: NE:d3dkmdt._D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
title: "_D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE"
author: windows-driver-content
description: The D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration indicates the pivot type in a call to DxgkDdiEnumVidPnCofuncModality.
old-location: display\d3dkmdt_enumcofuncmodality_pivot_type.htm
old-project: display
ms.assetid: ba99936a-e76a-4a34-b7cd-762a8f15732c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/D3DKMDT_EPT_VIDPNTARGET, D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE, D3DKMDT_EPT_NOPIVOT, D3DKMDT_EPT_SCALING, D3DKMDT_EPT_ROTATION, d3dkmdt/D3DKMDT_EPT_VIDPNSOURCE, d3dkmdt/D3DKMDT_EPT_SCALING, d3dkmdt/D3DKMDT_EPT_NOPIVOT, D3DKMDT_EPT_VIDPNTARGET, D3DKMDT_EPT_VIDPNSOURCE, DmEnums_5abafdb2-5a17-437b-b3e3-9c045c52d582.xml, d3dkmdt/D3DKMDT_EPT_ROTATION, D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration [Display Devices], _D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE, d3dkmdt/D3DKMDT_EPT_UNINITIALIZED, display.d3dkmdt_enumcofuncmodality_pivot_type, d3dkmdt/D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE, D3DKMDT_EPT_UNINITIALIZED
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
-	D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
---

# _D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration


## -description


The D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration indicates the pivot type in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>.


## -syntax


````
typedef enum _D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE { 
  D3DKMDT_EPT_UNINITIALIZED  = 0,
  D3DKMDT_EPT_VIDPNSOURCE    = 1,
  D3DKMDT_EPT_VIDPNTARGET    = 2,
  D3DKMDT_EPT_SCALING        = 3,
  D3DKMDT_EPT_ROTATION       = 4,
  D3DKMDT_EPT_NOPIVOT        = 5
} D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE;
````


## -enum-fields




### -field D3DKMDT_EPT_UNINITIALIZED

Indicates that a variable of type D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE has not yet been assigned a meaningful value.


### -field D3DKMDT_EPT_VIDPNSOURCE

Indicates that a video present source is the pivot of the enumeration.


### -field D3DKMDT_EPT_VIDPNTARGET

Indicates that a video present target is the pivot of the enumeration.


### -field D3DKMDT_EPT_SCALING

Indicates that the scaling transformation is the pivot of the enumeration.


### -field D3DKMDT_EPT_ROTATION

Indicates that the rotatation transformation is the pivot of the enumeration.


### -field D3DKMDT_EPT_NOPIVOT

Indicates that the enumeration has no pivot.


## -remarks


The <b>EnumPivotType</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_enumvidpncofuncmodality.md">DXGKARG_ENUMVIDPNCOFUNCMODALITY</a> structure is a D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE value.



## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

