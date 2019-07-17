---
UID: NS:d3dkmthk._D3DKMT_ADAPTERINFO
title: _D3DKMT_ADAPTERINFO (d3dkmthk.h)
description: Supplies configuration information about a graphics adapter.
old-location: display\d3dkmt_adapterinfo.htm
ms.assetid: 4b780fb7-f6d4-4248-882c-d0cc96106724
ms.date: 11/21/2018
ms.keywords: D3DKMT_ADAPTERINFO, D3DKMT_ADAPTERINFO structure [Display Devices], _D3DKMT_ADAPTERINFO, d3dkmthk/D3DKMT_ADAPTERINFO, display.d3dkmt_adapterinfo
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_ADAPTERINFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_ADAPTERINFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_ADAPTERINFO
---

# _D3DKMT_ADAPTERINFO structure


## -description

Supplies information about a adapter.

## -struct-fields

### -field hAdapter
*D3DKMT\_HANDLE* *hAdapter*

A handle to the adapter.

### -field AdapterLuid
*LUID AdapterLuid*

A LUID value that uniquely identifies the adapter, typically until the operating system is rebooted.
The LUID value changes whenever:
- the system is rebooted
- the adapter's driver is updated
- the adapter is disabled
- the adapter is disconnected

### -field NumOfSources
*ULONG NumOfSources*

The number of video present sources supported by the adapter.

### -field bPresentMoveRegionsPreferred
*BOOL bPresentMoveRegionsPreferred*

If <b>TRUE</b>, the adapter prefers move regions.

## -see-also
- [D3DKMT_ENUMADAPTERS2](ns-d3dkmthk-_d3dkmt_enumadapters2.md)

