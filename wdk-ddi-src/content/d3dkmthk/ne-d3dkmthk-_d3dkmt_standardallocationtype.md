---
UID: NE:d3dkmthk._D3DKMT_STANDARDALLOCATIONTYPE
title: "_D3DKMT_STANDARDALLOCATIONTYPE"
author: windows-driver-content
description: Used to give information on the allocation type.
old-location: display\d3dkmt-standardallocationtype.htm
old-project: display
ms.assetid: 7ce6d148-bfe8-4040-a4c1-ccd22fd07307
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMT_STANDARDALLOCATIONTYPE_EXISTINGHEAP, D3DKMT_STANDARDALLOCATIONTYPE_EXISTINGHEAP, display.d3dkmt-standardallocationtype, _D3DKMT_STANDARDALLOCATIONTYPE, D3DKMT_STANDARDALLOCATIONTYPE, d3dkmthk/D3DKMT_STANDARDALLOCATIONTYPE, D3DKMT_STANDARDALLOCATIONTYPE enumeration [Display Devices]
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
-	D3DKMT_STANDARDALLOCATIONTYPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_STANDARDALLOCATIONTYPE
---

# _D3DKMT_STANDARDALLOCATIONTYPE enumeration


## -description


Used to give information on the allocation type.


## -syntax


````
typedef enum _D3DKMT_STANDARDALLOCATIONTYPE { 
  D3DKMT_STANDARDALLOCATIONTYPE_EXISTINGHEAP  = 1
} D3DKMT_STANDARDALLOCATIONTYPE;
````


## -enum-fields




### -field D3DKMT_STANDARDALLOCATIONTYPE_EXISTINGHEAP

Indicates that the allocation type is an existing heap.

