---
UID: NS:d3dukmdt._DXGKVGPU_ESCAPE_READ_PCI_CONFIG
title: _DXGKVGPU_ESCAPE_READ_PCI_CONFIG
author: windows-driver-content
description: A structure used to read the PCI config for an escape.
old-location: display\dxgkvgpu_escape_read_pci_config.htm
old-project: display
ms.assetid: B6F4207F-B55A-4B36-883D-291E351742CA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKVGPU_ESCAPE_READ_PCI_CONFIG, DXGKVGPU_ESCAPE_READ_PCI_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: TBD
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKVGPU_ESCAPE_READ_PCI_CONFIG
req.alt-loc: d3dukmdt.h
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
req.typenames: DXGKVGPU_ESCAPE_READ_PCI_CONFIG
---

# _DXGKVGPU_ESCAPE_READ_PCI_CONFIG structure



## -description
A structure used to read the PCI config for an escape.



## -syntax

````
typedef struct _DXGKVGPU_ESCAPE_READ_PCI_CONFIG {
  DXGKVGPU_ESCAPE_HEAD Header;
  UINT                 Offset;
  UINT                 Size;
} DXGKVGPU_ESCAPE_READ_PCI_CONFIG;
````


## -struct-fields

### -field Header

The escape header being processed.


### -field Offset

Offset in bytes in the PCI config space.


### -field Size

Size in bytes to read.


## -remarks
