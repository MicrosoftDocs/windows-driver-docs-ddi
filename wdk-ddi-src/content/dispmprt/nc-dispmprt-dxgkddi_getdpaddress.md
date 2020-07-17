---
UID: NC:dispmprt.DXGKDDI_GETDPADDRESS
title: DXGKDDI_GETDPADDRESS
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: 
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
 - DXGKDDI_GETDPADDRESS
f1_keywords:
 - dispmprt//DXGKDDI_GETDPADDRESS
 - DXGKDDI_GETDPADDRESS
dev_langs:
 - c++
---

# DXGKDDI_GETDPADDRESS callback function

## -description

The **DXGKDDI_GETDPADDRESS** callback queries the DisplayPort (DP) address of a monitor connected through DP.

## -parameters

### -param Context

Context pointer provided when querying the interface.

### -param pArgs

Pointer to a [**DXGKARG_GETDPADDRESS**](ns-dispmprt-dxgkarg_getdpaddress.md) structure.

## -returns

**DXGKDDI_GETDPADDRESS** returns STATUS_SUCCESS if it succeeds; otherwise it returns an error code.

## -remarks

**DXGKDDI_GETDPADDRESS** is both for developmental and validation purposes.

For **TargetId** of a monitor connected through DP, the driver should return its DP address in the form of **RootPortIndex**, **NumLinks**, and DP Relative Address in **RelAddress**. **NumLinks** should be 0 if the DP monitor is directly connected to the GPU; otherwise, it should be the number of links between the root port and target device. The format of the Relative Address in **RelAddress** should follow the DP spec.

## -see-also

[**DXGKARG_GETDPADDRESS**](ns-dispmprt-dxgkarg_getdpaddress.md)
