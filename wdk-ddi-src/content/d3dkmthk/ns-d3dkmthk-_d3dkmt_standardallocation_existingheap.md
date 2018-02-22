---
UID: NS:d3dkmthk._D3DKMT_STANDARDALLOCATION_EXISTINGHEAP
title: "_D3DKMT_STANDARDALLOCATION_EXISTINGHEAP"
author: windows-driver-content
description: Holds information about the existing heap.
old-location: display\d3dkmt-standardallocation-existingheap.htm
old-project: display
ms.assetid: 7e97fb29-64a7-4fb5-b07e-a9810499cf1b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DKMT_STANDARDALLOCATION_EXISTINGHEAP, _D3DKMT_STANDARDALLOCATION_EXISTINGHEAP, display.d3dkmt-standardallocation-existingheap, d3dkmthk/D3DKMT_STANDARDALLOCATION_EXISTINGHEAP, D3DKMT_STANDARDALLOCATION_EXISTINGHEAP structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3DKMT_STANDARDALLOCATION_EXISTINGHEAP
product: Windows
targetos: Windows
req.typenames: D3DKMT_STANDARDALLOCATION_EXISTINGHEAP
---

# _D3DKMT_STANDARDALLOCATION_EXISTINGHEAP structure


## -description


Holds information about the existing heap.


## -syntax


````
typedef struct _D3DKMT_STANDARDALLOCATION_EXISTINGHEAP {
  SIZE_T Size;
} D3DKMT_STANDARDALLOCATION_EXISTINGHEAP;
````


## -struct-fields




### -field Size

Size in bytes of the existing heap.

