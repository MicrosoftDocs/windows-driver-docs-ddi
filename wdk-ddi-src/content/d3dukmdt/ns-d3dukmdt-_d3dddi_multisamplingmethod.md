---
UID: NS:d3dukmdt._D3DDDI_MULTISAMPLINGMETHOD
title: "_D3DDDI_MULTISAMPLINGMETHOD"
author: windows-driver-content
description: The D3DDDI_MULTISAMPLINGMETHOD structure describes a multiple-sampling method.
old-location: display\d3dddi_multisamplingmethod.htm
old-project: display
ms.assetid: 2838cb87-0cd5-4351-a477-00f75eca0896
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_MULTISAMPLINGMETHOD, D3DDDI_MULTISAMPLINGMETHOD structure [Display Devices], D3D_other_Structs_752f8e91-d298-437a-80c4-005e21ec0ddd.xml, _D3DDDI_MULTISAMPLINGMETHOD, d3dukmdt/D3DDDI_MULTISAMPLINGMETHOD, display.d3dddi_multisamplingmethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_MULTISAMPLINGMETHOD
product: Windows
targetos: Windows
req.typenames: D3DDDI_MULTISAMPLINGMETHOD
---

# _D3DDDI_MULTISAMPLINGMETHOD structure


## -description


The D3DDDI_MULTISAMPLINGMETHOD structure describes a multiple-sampling method.


## -syntax


````
typedef struct _D3DDDI_MULTISAMPLINGMETHOD {
  UINT NumSamples;
  UINT NumQualityLevels;
} D3DDDI_MULTISAMPLINGMETHOD;
````


## -struct-fields




### -field NumSamples

[out] The number of subpixels that are used in the multiple-sampling method (for example, 2 for 2x and 8 for 8x multiple-sampling).


### -field NumQualityLevels

[out] The upper bound on the quality range that is supported for the multiple-sampling method. The range includes values from 0 through the reported maximum quality setting.


## -remarks



The driver can partition its quality levels for a given multiple-sampling method into as many increments as it requires; however, each incremental step noticeably improves quality of the presented image.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_describeallocation.md">DXGKARG_DESCRIBEALLOCATION</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_describeallocation.md">DxgkDdiDescribeAllocation</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MULTISAMPLINGMETHOD structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

