---
UID: NS:dxva._DXVA_MVvalue
title: "_DXVA_MVvalue"
author: windows-driver-content
description: The DXVA_MVvalue structure is sent by the host decoder to the accelerator to specify the two-dimensional motion vector value.
old-location: display\dxva_mvvalue.htm
old-project: display
ms.assetid: 33b68e74-64ca-49e0-b469-96d430c2a5c0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dxvaref_4eeb8072-1676-479e-b92c-05d8ba9c4586.xml, LPDXVA_MVvalue, _DXVA_MVvalue, LPDXVA_MVvalue structure pointer [Display Devices], display.dxva_mvvalue, dxva/LPDXVA_MVvalue, dxva/DXVA_MVvalue, DXVA_MVvalue, *LPDXVA_MVvalue, DXVA_MVvalue structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxva.h
apiname:
-	DXVA_MVvalue
product: Windows
targetos: Windows
req.typenames: "*LPDXVA_MVvalue, DXVA_MVvalue"
---

# _DXVA_MVvalue structure


## -description


The DXVA_MVvalue structure is sent by the host decoder to the accelerator to specify the two-dimensional motion vector value.


## -syntax


````
typedef struct _DXVA_MVvalue {
  SHORT horz;
  SHORT vert;
} DXVA_MVvalue, *LPDXVA_MVvalue;
````


## -struct-fields




### -field horz

Specifies the horizontal component of the value of a motion vector. Contains a signed integer motion offset in half-sample units. The value of this member will be an even integer if the <b>bMVprecisionAndChromaRelation</b> member of <a href="..\dxva\ns-dxva-_dxva_pictureparameters.md">DXVA_PictureParameters</a> equals 2 (H.261-style motion supporting only integer-sample offsets).


### -field vert

Specifies the vertical component of the value of a motion vector. Contains a signed integer motion offset in half-sample units. The value of this member will be an even integer if the <b>bMVprecisionAndChromaRelation</b> member of <a href="..\dxva\ns-dxva-_dxva_pictureparameters.md">DXVA_PictureParameters</a> equals 2 (H.261-style motion supporting only integer-sample offsets).


## -remarks



The DXVA_MVvalue structure is used in the <a href="..\dxva\ns-dxva-_dxva_mbctrl_p_hostresiddiff_1.md">DXVA_MBctrl_P_HostResidDiff_1</a> and <a href="..\dxva\ns-dxva-_dxva_mbctrl_p_offhostidct_1.md">DXVA_MBctrl_P_OffHostIDCT_1</a> structures.




## -see-also

<a href="..\dxva\ns-dxva-_dxva_mbctrl_p_hostresiddiff_1.md">DXVA_MBctrl_P_HostResidDiff_1</a>



<a href="..\dxva\ns-dxva-_dxva_mbctrl_p_offhostidct_1.md">DXVA_MBctrl_P_OffHostIDCT_1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_MVvalue structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

