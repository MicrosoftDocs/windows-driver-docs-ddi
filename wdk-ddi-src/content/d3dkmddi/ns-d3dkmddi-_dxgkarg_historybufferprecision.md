---
UID: NS:d3dkmddi._DXGKARG_HISTORYBUFFERPRECISION
title: _DXGKARG_HISTORYBUFFERPRECISION (d3dkmddi.h)
description: Indicates info about the precision of history buffer data used by the display miniport driver.
old-location: display\dxgkarg_historybufferprecision.htm
ms.assetid: D55A8B5A-4133-4CE8-AD08-F551A3AEA42C
ms.date: 05/10/2018
keywords: ["DXGKARG_HISTORYBUFFERPRECISION structure"]
ms.keywords: DXGKARG_HISTORYBUFFERPRECISION, DXGKARG_HISTORYBUFFERPRECISION structure [Display Devices], _DXGKARG_HISTORYBUFFERPRECISION, d3dkmddi/DXGKARG_HISTORYBUFFERPRECISION, display.dxgkarg_historybufferprecision
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGKARG_HISTORYBUFFERPRECISION
f1_keywords:
 - _DXGKARG_HISTORYBUFFERPRECISION
 - d3dkmddi/_DXGKARG_HISTORYBUFFERPRECISION
 - DXGKARG_HISTORYBUFFERPRECISION
 - d3dkmddi/DXGKARG_HISTORYBUFFERPRECISION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - DXGKARG_HISTORYBUFFERPRECISION
---

# _DXGKARG_HISTORYBUFFERPRECISION structure


## -description

Indicates info about the precision of history buffer data used by the display miniport driver.

## -struct-fields

### -field PrecisionBits

The number of valid bits that are used in each time stamp. This number doesn't include bits used for junk values.

This precision value has three valid ranges:

| **Value** | **Meaning** | 
|:--|:--|
| 0 | No bits contain useful data, and the DirectX graphics kernel subsystem will call the [DxgkDdiFormatHistoryBuffer](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_formathistorybuffer) function to provide valid data to output to the Event Tracing for Windows (ETW) facility. When the driver processes this call, it sets a new precision value as the output parameter of the function. |
| 32 | The driver should log 32-bit time stamps using the full 32 bits of precision. | 
| 33–64 | The driver should log 64-bit time stamps. This value defines the number of bits used to store data per time stamp.<br/>To reduce the cost of formatting the data, the driver can include junk values in the 64-bit time stamps. For example, the driver could write 64-bit time stamps with 55 valid bits of precision. In this case the upper 9 bits are considered junk values and are stripped off by ETW. |


Values between 0 and 32 are unsupported and invalid.

If the hardware supports 64-bit time stamps but only 32 bits are usable, the driver must ensure that the data is presented correctly to the DirectX graphics kernel subsystem. If the driver has no other alternatives to present the data, it should provide the precision value when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_formathistorybuffer">DxgkDdiFormatHistoryBuffer</a> function is next called.

## -remarks

In a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function, the output data size,  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>.<b>OutputDataSize</b>, is:

```cpp
sizeof(DXGKARG_HISTORYBUFFERPRECISION) * m_DriverCaps.GpuEngineTopology.NbAsymetricProcessingNodes
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_formathistorybuffer">DxgkDdiFormatHistoryBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>

