---
UID: NS:d3d10umddi.D3D10_DDI_BOX
title: D3D10_DDI_BOX
author: windows-driver-content
description: The D3D10_DDI_BOX structure describes a volume.
old-location: display\d3d10_ddi_box.htm
old-project: display
ms.assetid: b09ea915-070d-4ebb-a40d-d60add5df3d8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D10_DDI_BOX, D3D10_DDI_BOX structure [Display Devices], UMDisplayDriver_Dx10param_Structs_11ac8e3e-48db-469b-a6e6-d42fd491d56e.xml, d3d10umddi/D3D10_DDI_BOX, display.d3d10_ddi_box
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3D10_DDI_BOX
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_BOX
---

# D3D10_DDI_BOX structure


## -description


The D3D10_DDI_BOX structure describes a volume.


## -syntax


````
typedef struct D3D10_DDI_BOX {
  LONG left;
  LONG top;
  LONG front;
  LONG right;
  LONG bottom;
  LONG back;
} D3D10_DDI_BOX;
````


## -struct-fields




### -field left

[in] The position of the left side of the box on the x-axis.


### -field top

[in] The position of the top of the box on the y-axis.


### -field front


      [in] The position of the front of the box on the z-axis.
     


### -field right

[in] The position of the right side of the box on the x-axis. Note that the width of the volume equals the value in the <b>right</b> member minus the value in the <b>left</b> member (that is, width = right – left). 


### -field bottom

[in] The position of the bottom of the box on the y-axis. Note that the height of the volume equals the value in the <b>bottom</b> member minus the value in the <b>top</b> member (that is, height = bottom – top). 


### -field back

[in] The position of the back of the box on the z-axis. Note that the depth of the volume equals the value in the <b>back</b> member minus the value in the <b>front</b> member (that is, depth = back – front). 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_BOX structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

