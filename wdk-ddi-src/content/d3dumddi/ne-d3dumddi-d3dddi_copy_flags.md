---
UID: NE:d3dumddi.D3DDDI_COPY_FLAGS
title: D3DDDI_COPY_FLAGS
author: windows-driver-content
description: Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource.
old-location: display\d3dddi_copy_flags.htm
old-project: display
ms.assetid: 6186dac4-4797-48f2-bb32-40a0d501bac7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: d3dumddi/D3DDDI_COPY_DISCARD, D3DDDI_COPY_NO_OVERWRITE, d3dumddi/D3DDDI_COPY_FLAGS, d3dumddi/D3DDDI_COPY_NO_OVERWRITE, D3DDDI_COPY_FLAGS, display.d3dddi_copy_flags, D3DDDI_COPY_DISCARD, D3DDDI_COPY_FLAGS enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dumddi.h
apiname:
-	D3DDDI_COPY_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_COPY_FLAGS
---

# D3DDDI_COPY_FLAGS enumeration


## -description


Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource.


## -syntax


````
typedef enum D3DDDI_COPY_FLAGS { 
  D3DDDI_COPY_NO_OVERWRITE  = 0x00000001,
  D3DDDI_COPY_DISCARD       = 0x00000002
} D3DDDI_COPY_FLAGS;
````


## -enum-fields




### -field D3DDDI_COPY_NO_OVERWRITE

The caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.


### -field D3DDDI_COPY_DISCARD

The user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.

