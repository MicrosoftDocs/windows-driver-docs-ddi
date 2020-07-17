---
UID: NC:dispmprt.DXGKDDI_QUERYDPCAPS
title: DXGKDDI_QUERYDPCAPS
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGKDDI_QUERYDPCAPS callback functions queries the DisplayPort (DP) capabilities of the GPU and driver supported.
tech.root: display
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_QUERYDPCAPS
f1_keywords:
 - dispmprt/DXGKDDI_QUERYDPCAPS
 - ""
dev_langs:
 - c++
---

# DXGKDDI_QUERYDPCAPS callback function

## -description

The **DXGKDDI_QUERYDPCAPS** callback functions queries the DisplayPort (DP) capabilities of the GPU and driver supported.

## -parameters

### -param Context

Context pointer provided when querying the interface.

### -param pArgs

Pointer to a [**DXGKARG_QUERYDPCAPS**](ns-dispmprt-dxgkarg_querydpcaps.md) structure in which to return the DP capabilities.

## -returns

**DXGKDDI_QUERYDPCAPS** returns STATUS_SUCCESS if it succeeds; otherwise it returns an error code.

## -remarks

The driver should return in **NumRootPorts** the number of DP capable connectors on the GPU, including the one for eDP internal panel. Subsequent transmission calls will refer to the DP connectors with **RootPortIndex** ranging from **0** to **NumRootPorts - 1**.

**DPVersionMajor** and **DPVersionMinor** is the highest version of DP protocol supported by the driver and GPU DP root ports of major/minor versions. For example, **DPVersionMajor == 1** and **DPVersionMinor == 1** is for DP protocol 1.1, and **DPVersionMajor == 1** and **DPVersionMinor == 2** is for DP protocol 1.2.

## -see-also

[**DXGKARG_QUERYDPCAPS**](ns-dispmprt-dxgkarg_querydpcaps.md)

[**DXGKDDI_DPAUXIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpauxiotransmission.md)

[**DXGKDDI_DPI2CIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpi2ciotransmission.md)

[**DXGKDDI_DPSBMTRANSMISSION**](nc-dispmprt-dxgkddi_dpsbmtransmission.md)
