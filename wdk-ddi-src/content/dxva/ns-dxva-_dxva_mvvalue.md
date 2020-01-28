---
UID: NS:dxva._DXVA_MVvalue
title: _DXVA_MVvalue (dxva.h)
description: The DXVA_MVvalue structure is sent by the host decoder to the accelerator to specify the two-dimensional motion vector value.
old-location: display\dxva_mvvalue.htm
tech.root: display
ms.assetid: 33b68e74-64ca-49e0-b469-96d430c2a5c0
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_MVvalue, DXVA_MVvalue, DXVA_MVvalue structure [Display Devices], LPDXVA_MVvalue, LPDXVA_MVvalue structure pointer [Display Devices], _DXVA_MVvalue, display.dxva_mvvalue, dxva/DXVA_MVvalue, dxva/LPDXVA_MVvalue, dxvaref_4eeb8072-1676-479e-b92c-05d8ba9c4586.xml"
f1_keywords:
 - "dxva/DXVA_MVvalue"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_MVvalue
product:
- Windows
targetos: Windows
req.typenames: DXVA_MVvalue, *LPDXVA_MVvalue
---

# _DXVA_MVvalue structure


## -description


The DXVA_MVvalue structure is sent by the host decoder to the accelerator to specify the two-dimensional motion vector value.


## -struct-fields




### -field horz

Specifies the horizontal component of the value of a motion vector. Contains a signed integer motion offset in half-sample units. The value of this member will be an even integer if the <b>bMVprecisionAndChromaRelation</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a> equals 2 (H.261-style motion supporting only integer-sample offsets).


### -field vert

Specifies the vertical component of the value of a motion vector. Contains a signed integer motion offset in half-sample units. The value of this member will be an even integer if the <b>bMVprecisionAndChromaRelation</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a> equals 2 (H.261-style motion supporting only integer-sample offsets).


## -remarks



The DXVA_MVvalue structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_hostresiddiff_1">DXVA_MBctrl_P_HostResidDiff_1</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_offhostidct_1">DXVA_MBctrl_P_OffHostIDCT_1</a> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_hostresiddiff_1">DXVA_MBctrl_P_HostResidDiff_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_offhostidct_1">DXVA_MBctrl_P_OffHostIDCT_1</a>
 

 

