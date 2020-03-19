---
UID: NS:d3dkmddi._DXGK_QUERYGPUMMUCAPSIN
title: _DXGK_QUERYGPUMMUCAPSIN (d3dkmddi.h)
description: The DXGK_QUERYGPUMMUCAPSIN structure holds the index of the adapter being queried.
old-location: display\dxgk_querygpummucapsin.htm
ms.assetid: 8DFD307F-DD4E-4321-AD97-78A5D67687B0
ms.date: 05/10/2018
keywords: ["_DXGK_QUERYGPUMMUCAPSIN structure"]
ms.keywords: DXGK_QUERYGPUMMUCAPSIN, DXGK_QUERYGPUMMUCAPSIN structure [Display Devices], _DXGK_QUERYGPUMMUCAPSIN, d3dkmddi/DXGK_QUERYGPUMMUCAPSIN, display.dxgk_querygpummucapsin
f1_keywords:
 - "d3dkmddi/DXGK_QUERYGPUMMUCAPSIN"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_QUERYGPUMMUCAPSIN
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYGPUMMUCAPSIN
---

# _DXGK_QUERYGPUMMUCAPSIN structure


## -description


The <b>DXGK_QUERYGPUMMUCAPSIN</b> structure holds the index of the adapter being queried.


## -struct-fields




### -field PhysicalAdapterIndex

A zero-based physical adapter index (engine ordinal) for which the data is queried.


## -remarks



To get GpuMmu caps Dxgkrnl calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> with the following parameters:

<pre class="syntax" xml:space="preserve"><code>DXGKARG_QUERYADAPTERINFO::Type = DXGKQAITYPE_GPUMMUCAPS;
DXGKARG_QUERYADAPTERINFO::pInputData = buffer of DXGK_QUERYGPUMMUCAPSIN type
DXGKARG_QUERYADAPTERINFO::InputDataSize = sizeof(DXGK_QUERYGPUMMUCAPSIN);
DXGKARG_QUERYADAPTERINFO::pOutputData = pointer to DXGK_GPUMMUCAPS
DXGKARG_QUERYADAPTERINFO::OutputDataSize = sizeof(DXGK_GPUMMUCAPS);</code></pre>


