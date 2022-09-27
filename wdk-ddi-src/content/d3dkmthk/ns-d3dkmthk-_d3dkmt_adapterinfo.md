---
UID: NS:d3dkmthk._D3DKMT_ADAPTERINFO
title: D3DKMT_ADAPTERINFO (d3dkmthk.h)
description: Supplies configuration information about a graphics adapter.
old-location: display\d3dkmt_adapterinfo.htm
ms.date: 08/30/2022
keywords: ["D3DKMT_ADAPTERINFO structure"]
ms.keywords: D3DKMT_ADAPTERINFO, D3DKMT_ADAPTERINFO structure [Display Devices], _D3DKMT_ADAPTERINFO, d3dkmthk/D3DKMT_ADAPTERINFO, display.d3dkmt_adapterinfo
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_ADAPTERINFO
f1_keywords:
 - _D3DKMT_ADAPTERINFO
 - d3dkmthk/_D3DKMT_ADAPTERINFO
 - D3DKMT_ADAPTERINFO
 - d3dkmthk/D3DKMT_ADAPTERINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_ADAPTERINFO
 - D3DKMT_ADAPTERINFO
---

# D3DKMT_ADAPTERINFO structure

## -description

Supplies information about a adapter.

## -struct-fields

### -field hAdapter

A handle to the adapter.

### -field AdapterLuid

A LUID value that uniquely identifies the adapter, typically until the operating system is rebooted. The LUID value changes whenever:

- the system is rebooted
- the adapter's driver is updated
- the adapter is disabled
- the adapter is disconnected

### -field NumOfSources

The number of video present sources supported by the adapter.

### -field bPrecisePresentRegionsPreferred

If **TRUE**, the adapter prefers precise present regions.

## -see-also

[**D3DKMT_ENUMADAPTERS2**](ns-d3dkmthk-_d3dkmt_enumadapters2.md)
