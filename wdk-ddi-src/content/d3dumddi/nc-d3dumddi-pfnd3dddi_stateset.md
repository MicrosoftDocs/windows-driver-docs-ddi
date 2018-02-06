---
UID: NC:d3dumddi.PFND3DDDI_STATESET
title: PFND3DDDI_STATESET
author: windows-driver-content
description: The StateSet function sets a state block.
old-location: display\stateset.htm
old-project: display
ms.assetid: 2c298de6-a3d9-45c7-ab60-dc9124eed1bb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.stateset, StateSet callback function [Display Devices], StateSet, PFND3DDDI_STATESET, PFND3DDDI_STATESET, d3dumddi/StateSet, UserModeDisplayDriver_Functions_ca9843ce-a32d-4d81-844a-213b7fe6c6e0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	StateSet
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_STATESET callback


## -description


The <i>StateSet</i> function sets a state block.


## -prototype


````
PFND3DDDI_STATESET StateSet;

__checkReturn HRESULT APIENTRY StateSet(
  _In_ HANDLE             hDevice,
  _In_ D3DDDIARG_STATESET *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_stateset.md">D3DDDIARG_STATESET</a> structure that describes how to set the state block.


## -returns


<i>StateSet</i> returns S_OK or an appropriate error result if the state block is not successfully set.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_stateset.md">D3DDDIARG_STATESET</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_STATESET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

