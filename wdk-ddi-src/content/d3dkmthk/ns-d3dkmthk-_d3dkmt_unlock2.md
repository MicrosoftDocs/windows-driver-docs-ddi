---
UID: NS:d3dkmthk._D3DKMT_UNLOCK2
title: "_D3DKMT_UNLOCK2"
author: windows-driver-content
description: D3DKMT_UNLOCK2 describes an allocation to unlock.
old-location: display\d3dkmt_unlock2.htm
old-project: display
ms.assetid: 8651297B-BCF7-42A2-9175-D9D072E052D6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 2, 3, C, D, D3DKMT_UNLOCK2, D3DKMT_UNLOCK2 structure [Display Devices], K, L, M, N, O, T, U, _, _D3DKMT_UNLOCK2, d3dkmthk/D3DKMT_UNLOCK2, display.d3dkmt_unlock2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
apiname:
-	D3DKMT_UNLOCK2
product: Windows
targetos: Windows
req.typenames: D3DKMT_UNLOCK2
---

# _D3DKMT_UNLOCK2 structure


## -description


<b>D3DKMT_UNLOCK2</b> describes an allocation to unlock.


## -syntax


````
typedef struct _D3DKMT_UNLOCK2 {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hAllocation;
} D3DKMT_UNLOCK2;
````


## -struct-fields




### -field hDevice

The handle to the device.


### -field hAllocation

The handle to the allocation to unlock.

