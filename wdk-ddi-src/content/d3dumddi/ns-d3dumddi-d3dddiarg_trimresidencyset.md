---
UID: NS:d3dumddi.D3DDDIARG_TRIMRESIDENCYSET
title: D3DDDIARG_TRIMRESIDENCYSET
author: windows-driver-content
description: D3DDDIARG_TRIMRESIDENCYSET is used with pfnTrimResidencySet by a user mode driver to trim the residency list for a given device.
old-location: display\d3dddiarg_trimresidencyset.htm
old-project: display
ms.assetid: DEF219B9-115A-4B61-8014-266730CEBD30
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_TRIMRESIDENCYSET, display.d3dddiarg_trimresidencyset, d3dumddi/D3DDDIARG_TRIMRESIDENCYSET, D3DDDIARG_TRIMRESIDENCYSET structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_TRIMRESIDENCYSET
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_TRIMRESIDENCYSET
---

# D3DDDIARG_TRIMRESIDENCYSET structure


## -description


<b>D3DDDIARG_TRIMRESIDENCYSET</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_trimresidencyset.md">pfnTrimResidencySet</a> by a user mode driver to trim the residency list for a given device.


## -syntax


````
typedef struct D3DDDIARG_TRIMRESIDENCYSET {
  D3DDDI_TRIMRESIDENCYSET_FLAGS TrimFlags;
  UINT64                        NumBytesToTrim;
} D3DDDIARG_TRIMRESIDENCYSET;
````


## -struct-fields




### -field TrimFlags

The trimming behavior flags.


### -field NumBytesToTrim

When <b>TrimToBudget</b> is set, this value specifies how much the application should evict in order to meet its current memory budget.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_trimresidencyset.md">pfnTrimResidencySet</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_TRIMRESIDENCYSET structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

