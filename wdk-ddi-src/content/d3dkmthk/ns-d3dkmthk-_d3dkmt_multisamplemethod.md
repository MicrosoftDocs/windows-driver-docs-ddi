---
UID: NS:d3dkmthk._D3DKMT_MULTISAMPLEMETHOD
title: "_D3DKMT_MULTISAMPLEMETHOD"
author: windows-driver-content
description: The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.
old-location: display\d3dkmt_multisamplemethod.htm
old-project: display
ms.assetid: 6cdc0665-61e6-4c13-9b15-46ce301febec
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, D, D3DKMT_MULTISAMPLEMETHOD, D3DKMT_MULTISAMPLEMETHOD structure [Display Devices], E, H, I, K, L, M, O, OpenGL_Structs_0617065f-aa53-4b1a-9a3f-e135972d4852.xml, P, S, T, U, _, _D3DKMT_MULTISAMPLEMETHOD, d3dkmthk/D3DKMT_MULTISAMPLEMETHOD, display.d3dkmt_multisamplemethod"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
apiname:
-	D3DKMT_MULTISAMPLEMETHOD
product: Windows
targetos: Windows
req.typenames: D3DKMT_MULTISAMPLEMETHOD
---

# _D3DKMT_MULTISAMPLEMETHOD structure


## -description


The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.


## -syntax


````
typedef struct _D3DKMT_MULTISAMPLEMETHOD {
  UINT NumSamples;
  UINT NumQualityLevels;
  UINT Reserved;
} D3DKMT_MULTISAMPLEMETHOD;
````


## -struct-fields




### -field NumSamples

[out] The number of subpixels that are used in the multiple-sampling method (for example, 2 for 2x and 8 for 8x multiple-sampling).


### -field NumQualityLevels

[out] The upper bound on the quality range that is supported for the multiple-sampling method. The range extends from zero through the reported maximum quality setting.


### -field Reserved

[out] Reserved.


## -remarks



The driver can partition its quality levels for a given multiple-sampling method into as many increments as it requires, with the condition that each incremental step noticeably improves the quality of the presented image.




## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetmultisamplemethodlist.md">D3DKMTGetMultisampleMethodList</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist.md">D3DKMT_GETMULTISAMPLEMETHODLIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_MULTISAMPLEMETHOD structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

