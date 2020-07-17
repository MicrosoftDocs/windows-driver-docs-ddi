---
UID: NS:dispmprt._DXGKARG_QUERYDPCAPS
title: DXGKARG_QUERYDPCAPS
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGKARG_QUERYDPCAPS structure is a parameter for the DXGKDDI_QUERYDPCAPS callback.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10. version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_QUERYDPCAPS, *PDXGKARG_QUERYDPCAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_QUERYDPCAPS
 - DXGKARG_QUERYDPCAPS
f1_keywords:
 - dispmprt/_DXGKARG_QUERYDPCAPS
 - dispmprt/DXGKARG_QUERYDPCAPS
 - ""
dev_langs:
 - c++
---

# DXGKARG_QUERYDPCAPS structure

## -description

The **DXGKARG_QUERYDPCAPS** structure is a parameter for the [**DXGKDDI_QUERYDPCAPS**](nc-dispmprt-dxgkddi_querydpcaps.md) callback.

## -struct-fields

### -field NumRootPorts

Number of DisplayPort (DP) capable connectors on the GPU, including the one for the eDP internal panel.

### -field DPVersionMajor

Value that represents the major version of the DP protocol.

### -field DPVersionMinor

Value that represents the minor version of the DP protocol.

## -remarks

Subsequent transmission calls will refer to the DP connectors with **RootPortIndex** ranging from **0** to **NumRootPorts - 1**.

**DPVersionMajor** and **DPVersionMinor** is the highest version of the DP protocol supported by the driver and GPU DP root ports of major/minor versions. For example, **DPVersionMajor == 1** and **DPVersionMinor == 1** represent DP protocol 1.1, **DPVersionMajor == 1** and **DPVersionMinor == 2** is for 1.2, and so forth.

## -see-also

[**DXGKDDI_DPAUXIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpauxiotransmission.md)

[**DXGKDDI_DPI2CIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpi2ciotransmission.md)

[**DXGKDDI_DPSBMTRANSMISSION**](nc-dispmprt-dxgkddi_dpsbmtransmission.md)

[**DXGKDDI_QUERYDPCAPS**](nc-dispmprt-dxgkddi_querydpcaps.md)
