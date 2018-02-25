---
UID: NE:d3dkmthk._D3DKMT_PNP_KEY_TYPE
title: "_D3DKMT_PNP_KEY_TYPE"
author: windows-driver-content
description: An enum that indicates the type of PNP key.
old-location: display\d3dkmt_pnp_key_type.htm
old-project: display
ms.assetid: 48B173D5-56C3-4611-BC55-CB7A25D05352
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, D, D3DKMT_PNP_KEY_HARDWARE, D3DKMT_PNP_KEY_SOFTWARE, D3DKMT_PNP_KEY_TYPE, D3DKMT_PNP_KEY_TYPE enumeration [Display Devices], E, K, M, N, P, T, Y, _, _D3DKMT_PNP_KEY_TYPE, d3dkmthk/D3DKMT_PNP_KEY_HARDWARE, d3dkmthk/D3DKMT_PNP_KEY_SOFTWARE, d3dkmthk/D3DKMT_PNP_KEY_TYPE, display.d3dkmt_pnp_key_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: 
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_PNP_KEY_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_PNP_KEY_TYPE
---

# _D3DKMT_PNP_KEY_TYPE enumeration


## -description


An enum that indicates the type of PNP key. 


## -syntax


````
typedef enum _D3DKMT_PNP_KEY_TYPE { 
  D3DKMT_PNP_KEY_HARDWARE  = 1,
  D3DKMT_PNP_KEY_SOFTWARE  = 2
} D3DKMT_PNP_KEY_TYPE;
````


## -enum-fields




### -field D3DKMT_PNP_KEY_HARDWARE

Indicates that the key is a hardware key..


### -field D3DKMT_PNP_KEY_SOFTWARE

Indicates that the key is a software key.

