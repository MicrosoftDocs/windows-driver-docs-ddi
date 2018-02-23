---
UID: NS:d3dkmddi._DXGKARG_ENUMVIDPNCOFUNCMODALITY
title: "_DXGKARG_ENUMVIDPNCOFUNCMODALITY"
author: windows-driver-content
description: The DXGKARG_ENUMVIDPNCOFUNCMODALITY structure contains arguments for the DxgkDdiEnumVidPnCofuncModality function.
old-location: display\dxgkarg_enumvidpncofuncmodality.htm
old-project: display
ms.assetid: a67c9e20-68bf-45d5-bbf0-d324643b2a5d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DmStructs_7b6ad975-cf77-450d-9190-f74711cafe71.xml, DXGKARG_ENUMVIDPNCOFUNCMODALITY, _DXGKARG_ENUMVIDPNCOFUNCMODALITY, display.dxgkarg_enumvidpncofuncmodality, d3dkmddi/DXGKARG_ENUMVIDPNCOFUNCMODALITY, DXGKARG_ENUMVIDPNCOFUNCMODALITY structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_ENUMVIDPNCOFUNCMODALITY
product: Windows
targetos: Windows
req.typenames: DXGKARG_ENUMVIDPNCOFUNCMODALITY
---

# _DXGKARG_ENUMVIDPNCOFUNCMODALITY structure


## -description


The DXGKARG_ENUMVIDPNCOFUNCMODALITY structure contains arguments for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> function. The <i>DxgkDdiEnumVidPnCofuncModality</i> function makes the source and target mode sets of a VidPN cofunctional with the VidPN's topology and the modes that have already been pinned.


## -syntax


````
typedef struct _DXGKARG_ENUMVIDPNCOFUNCMODALITY {
  D3DKMDT_HVIDPN                        hConstrainingVidPn;
  D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE EnumPivotType;
  DXGK_ENUM_PIVOT                       EnumPivot;
} DXGKARG_ENUMVIDPNCOFUNCMODALITY;
````


## -struct-fields




### -field hConstrainingVidPn

A handle to the VidPn object for which the cofunctional modes are being requested.


### -field EnumPivotType

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_enumcofuncmodality_pivot_type.md">D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE</a> enumerator that supplies the enumeration pivot type.


### -field EnumPivot

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_enum_pivot.md">DXGK_ENUM_PIVOT</a> structure.


## -remarks



If a particular video present source or target is designated as the pivot of the enumeration, then <i>DxgkDdiEnumVidPnCofuncModality</i> must not change the mode set for that source or target.

The D3DKMDT_HVIDPN data type is defined in <i>D3dkmdt.h</i>. The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_enum_pivot.md">DXGK_ENUM_PIVOT</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>



<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_enumcofuncmodality_pivot_type.md">D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_ENUMVIDPNCOFUNCMODALITY structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

