---
UID: NC:d3dumddi.PFND3DDDI_TRIMRESIDENCYSET
title: PFND3DDDI_TRIMRESIDENCYSET
author: windows-driver-content
description: pfnTrimResidencySet is used to trim the residency list for a given device. User mode drivers are required to implement this callback in order to participate in the new memory residency model.
old-location: display\pfntrimresidencyset.htm
old-project: display
ms.assetid: 192F419C-F38F-4B42-8111-86D58D6781DA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfntrimresidencyset, pfnTrimResidencySet callback function [Display Devices], pfnTrimResidencySet, PFND3DDDI_TRIMRESIDENCYSET, PFND3DDDI_TRIMRESIDENCYSET, d3dukmdt/pfnTrimResidencySet
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
apiname:
-	pfnTrimResidencySet
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_TRIMRESIDENCYSET callback


## -description


<b>pfnTrimResidencySet</b> is used to trim the residency list for a given device. User mode drivers are required to implement this callback in order to participate in the new memory residency model.


## -prototype


````
PFND3DDDI_TRIMRESIDENCYSET pfnTrimResidencySet;

HRESULT APIENTRY CALLBACK* pfnTrimResidencySet(
  _In_ HANDLE                     hDevice,
  _In_ D3DDDIARG_TRIMRESIDENCYSET *pData
)
{ ... }
````


## -parameters




#### - hDevice [in]

A handle to the display device.


### -param *






#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_trimresidencyset.md">D3DDDIARG_TRIMRESIDENCYSET</a> structure that provides the details of the requested operation.




## -returns


If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_trimresidencyset.md">D3DDDIARG_TRIMRESIDENCYSET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_TRIMRESIDENCYSET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

