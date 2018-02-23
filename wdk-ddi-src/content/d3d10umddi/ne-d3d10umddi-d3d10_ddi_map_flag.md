---
UID: NE:d3d10umddi.D3D10_DDI_MAP_FLAG
title: D3D10_DDI_MAP_FLAG
author: windows-driver-content
description: The D3D10_DDI_MAP_FLAG enumeration type contains flags that identify how to map to a subresource in a call to the driver's ResourceMap function.
old-location: display\d3d10_ddi_map_flag.htm
old-project: display
ms.assetid: e17ca347-6514-47df-9373-5d33fc7f8e5c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3D10_DDI_MAP_FLAG_MASK, D3D10_DDI_MAP_FLAG_DONOTWAIT, d3d10umddi/D3D10_DDI_MAP_FLAG, d3d10umddi/D3D10_DDI_MAP_FLAG_MASK, d3d10umddi/D3D10_DDI_MAP_FLAG_DONOTWAIT, display.d3d10_ddi_map_flag, UMDisplayDriver_Dx10param_Structs_ff1e6692-48bb-4381-831a-3d090bbb6f3f.xml, D3D10_DDI_MAP_FLAG enumeration [Display Devices], D3D10_DDI_MAP_FLAG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_DDI_MAP_FLAG
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_MAP_FLAG
---

# D3D10_DDI_MAP_FLAG enumeration


## -description


The D3D10_DDI_MAP_FLAG enumeration type contains flags that identify how to map to a subresource in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function.


## -syntax


````
typedef enum D3D10_DDI_MAP_FLAG { 
  D3D10_DDI_MAP_FLAG_DONOTWAIT  = 0x00100000L,
  D3D10_DDI_MAP_FLAG_MASK       = 0x00100000L
} D3D10_DDI_MAP_FLAG;
````


## -enum-fields




### -field D3D10_DDI_MAP_FLAG_DONOTWAIT

The driver can call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function to set the ERR_WASSTILLDRAWING error code if contention exists between an application and hardware when the driver receives the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>.


### -field D3D10_DDI_MAP_FLAG_MASK

A mask value that indicates the valid bitfields in a bitwise OR combination of the values from this enumeration. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_MAP_FLAG enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

