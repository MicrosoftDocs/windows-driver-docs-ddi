---
UID: NS:d3dukmdt._DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG
title: _DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG
author: windows-driver-content
description: Used to write to the PCI config space.
old-location: display\dxgkvgpu_escape_write_pci_config.htm
old-project: display
ms.assetid: 2B0902DB-B59C-4DC5-A944-02ACE9DA16DC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG, display.dxgkvgpu_escape_write_pci_config, DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG, d3dukmdt/DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG, DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
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
-	d3dukmdt.h
apiname: 
-	DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG
product: Windows
targetos: Windows
req.typenames: DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG
---

# _DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG structure


## -description


Used to write to the PCI config space.


## -syntax


````
typedef struct _DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG {
  UINT Offset;
  UINT Size;
} DXGKVGPU_ESCAPE_WRITE_PCI_CONFIG;
````


## -struct-fields




### -field Header

 


### -field Offset

Offset, in bytes, in the PCI config space.


### -field Size

Size, in bytes, to write

