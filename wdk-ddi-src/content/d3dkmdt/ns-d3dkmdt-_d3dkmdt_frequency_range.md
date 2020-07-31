---
UID: NS:d3dkmdt._D3DKMDT_FREQUENCY_RANGE
title: _D3DKMDT_FREQUENCY_RANGE (d3dkmdt.h)
description: The D3DKMDT_FREQUENCY_RANGE structure contains the minimum and maximum refresh rates supported by a monitor.
old-location: display\d3dkmdt_frequency_range.htm
tech.root: display
ms.assetid: f826f949-b37f-4c48-80d9-b6ef640e1f00
ms.date: 05/10/2018
keywords: ["_D3DKMDT_FREQUENCY_RANGE structure"]
ms.keywords: D3DKMDT_FREQUENCY_RANGE, D3DKMDT_FREQUENCY_RANGE structure [Display Devices], DmStructs_63b22220-c9fc-4eac-a725-caa0f5c38eba.xml, _D3DKMDT_FREQUENCY_RANGE, d3dkmdt/D3DKMDT_FREQUENCY_RANGE, display.d3dkmdt_frequency_range
f1_keywords:
 - "d3dkmdt/D3DKMDT_FREQUENCY_RANGE"
 - "D3DKMDT_FREQUENCY_RANGE"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- D3DKMDT_FREQUENCY_RANGE
targetos: Windows
req.typenames: D3DKMDT_FREQUENCY_RANGE
---

# _D3DKMDT_FREQUENCY_RANGE structure


## -description


The D3DKMDT_FREQUENCY_RANGE structure contains the minimum and maximum refresh rates supported by a monitor.


## -struct-fields




### -field MinVSyncFreq

The minimum vertical refresh rate, in Hz, supported by the monitor.


### -field MaxVSyncFreq

The maximum vertical refresh rate, in Hz, supported by the monitor.


### -field MinHSyncFreq

The minimum horizontal refresh rate, in Hz, supported by the monitor.


### -field MaxHSyncFreq

The maximum horizontal refresh rate, in Hz, supported by the monitor.


## -remarks



The <b>RangeLimits</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_frequency_range">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure is a D3DKMDT_FREQUENCY_RANGE structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor Frequency Range Set Interface</a>
 

 

