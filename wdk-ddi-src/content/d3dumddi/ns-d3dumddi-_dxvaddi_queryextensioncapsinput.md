---
UID: NS:d3dumddi._DXVADDI_QUERYEXTENSIONCAPSINPUT
title: "_DXVADDI_QUERYEXTENSIONCAPSINPUT"
author: windows-driver-content
description: The DXVADDI_QUERYEXTENSIONCAPSINPUT structure describes a capability of an extension GUID that information is requested for.
old-location: display\dxvaddi_queryextensioncapsinput.htm
old-project: display
ms.assetid: 6907eb45-8d29-4cdc-80eb-2d8cafbbd9bd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA2_Structs_82433e94-79b3-4398-a38e-7f7a99cc09be.xml, DXVADDI_QUERYEXTENSIONCAPSINPUT, DXVADDI_QUERYEXTENSIONCAPSINPUT structure [Display Devices], _DXVADDI_QUERYEXTENSIONCAPSINPUT, d3dumddi/DXVADDI_QUERYEXTENSIONCAPSINPUT, display.dxvaddi_queryextensioncapsinput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	DXVADDI_QUERYEXTENSIONCAPSINPUT
product: Windows
targetos: Windows
req.typenames: DXVADDI_QUERYEXTENSIONCAPSINPUT
---

# _DXVADDI_QUERYEXTENSIONCAPSINPUT structure


## -description


The DXVADDI_QUERYEXTENSIONCAPSINPUT structure describes a capability of an extension GUID that information is requested for.


## -struct-fields




### -field pGuid

[in] A pointer to a GUID that represents the extension device type. 


### -field CapType

[in] A capability type that information is requested for. A capability type can apply to one of the following categories of video acceleration:

<ul>
<li>
DXVADDI_EXTENSION_CATEGORY_DECODER (0x0001)

</li>
<li>
DXVADDI_EXTENSION_CATEGORY_ENCODER (0x0002)

</li>
<li>
DXVADDI_EXTENSION_CATEGORY_PROCESSOR (0x0004)

</li>
<li>
DXVADDI_EXTENSION_CATEGORY_ALL (0x0007)

</li>
</ul>
Extension capability types can be defined from DXVADDI_EXTENSION_CAPTYPE_MIN (300) to DXVADDI_EXTENSION_CAPTYPE_MAX (400).


### -field pPrivate

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562916">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to retrieve information about the extension capability.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562916">DXVADDI_PRIVATEDATA</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

