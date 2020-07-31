---
UID: NS:d3dkmddi._DXGK_QUERYPAGETABLELEVELDESCIN
title: _DXGK_QUERYPAGETABLELEVELDESCIN (d3dkmddi.h)
description: The DXGK_QUERYPAGETABLELEVELDESCIN structure is used to request page level descriptors from the Dxgkrnl Interface.
old-location: display\dxgk_querypagetableleveldescin.htm
ms.assetid: 1B13BBB1-4184-4166-A61F-CC266D0391BF
ms.date: 05/10/2018
keywords: ["_DXGK_QUERYPAGETABLELEVELDESCIN structure"]
ms.keywords: DXGK_QUERYPAGETABLELEVELDESCIN, DXGK_QUERYPAGETABLELEVELDESCIN structure [Display Devices], _DXGK_QUERYPAGETABLELEVELDESCIN, d3dkmddi/DXGK_QUERYPAGETABLELEVELDESCIN, display.dxgk_querypagetableleveldescin
f1_keywords:
 - "d3dkmddi/DXGK_QUERYPAGETABLELEVELDESCIN"
 - "DXGK_QUERYPAGETABLELEVELDESCIN"
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
- DXGK_QUERYPAGETABLELEVELDESCIN
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYPAGETABLELEVELDESCIN
---

# _DXGK_QUERYPAGETABLELEVELDESCIN structure


## -description


The <b>DXGK_QUERYPAGETABLELEVELDESCIN</b> structure is used to request page level descriptors from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Dxgkrnl Interface</a>.


## -struct-fields




### -field LevelIndex

A zero-based physical adapter index (engine ordinal) for which the data is queried.


### -field PhysicalAdapterIndex

A zero-based page table level index for the information requested.


## -remarks



To get page table level descriptors Dxgkrnl calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> with the following parameters:

<pre class="syntax" xml:space="preserve"><code>DXGKARG_QUERYADAPTERINFO::Type = DXGKQAITYPE_PAGETABLELEVELDESC;
DXGKARG_QUERYADAPTERINFO::pInputData = DXGK_QUERYPAGETABLELEVELDESCIN 
DXGKARG_QUERYADAPTERINFO::InputDataSize = sizeof(QUERYPAGETABLELEVELDESCIN)
DXGKARG_QUERYADAPTERINFO::pOutputData = pointer to DXGK_PAGE_TABLE_LEVEL_DESC
DXGKARG_QUERYADAPTERINFO::OutputDataSize = sizeof(DXGK_PAGE_TABLE_LEVEL_DESC);
</code></pre>


