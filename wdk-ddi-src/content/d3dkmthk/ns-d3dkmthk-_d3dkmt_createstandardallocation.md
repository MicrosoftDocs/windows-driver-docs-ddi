---
UID: NS:d3dkmthk._D3DKMT_CREATESTANDARDALLOCATION
title: _D3DKMT_CREATESTANDARDALLOCATION
author: windows-driver-content
description: Used to create a standard allocation.
old-location: display\d3dkmt-createstandardallocation.htm
old-project: display
ms.assetid: 7698ab93-68af-479d-97a4-c45ac84b0710
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_CREATESTANDARDALLOCATION, D3DKMT_CREATESTANDARDALLOCATION
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
req.alt-api: D3DKMT_CREATESTANDARDALLOCATION
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_CREATESTANDARDALLOCATION
---

# _D3DKMT_CREATESTANDARDALLOCATION structure



## -description
Used to create a standard allocation.



## -syntax

````
typedef struct _D3DKMT_CREATESTANDARDALLOCATION {
  D3DKMT_STANDARDALLOCATIONTYPE        Type;
  union {
    D3DKMT_STANDARDALLOCATION_EXISTINGHEAP ExistingHeapData;
  };
  D3DKMT_CREATESTANDARDALLOCATIONFLAGS Flags;
} D3DKMT_CREATESTANDARDALLOCATION;
````


## -struct-fields

### -field Type

The type of the standard allocation.


### -field ExistingHeapData

Holds information on the existing heap.


### -field Flags

Holds the flags needed to create a standard allocation.


## -remarks
