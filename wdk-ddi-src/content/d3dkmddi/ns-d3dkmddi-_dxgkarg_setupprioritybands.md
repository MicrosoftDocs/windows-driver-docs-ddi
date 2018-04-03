---
UID: NS:d3dkmddi._DXGKARG_SETUPPRIORITYBANDS
title: _DXGKARG_SETUPPRIORITYBANDS
author: windows-driver-content
description:
ms.assetid: 971b5d7f-5423-476a-a89d-b1d3f7a84301
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_SETUPPRIORITYBANDS, DXGKARG_SETUPPRIORITYBANDS,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_SETUPPRIORITYBANDS
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGKARG_SETUPPRIORITYBANDS
product: Windows
targetos: Windows
---

# _DXGKARG_SETUPPRIORITYBANDS structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Arguments used in a call to [DxgkddiSetupPriorityBands](nc-d3dkmddi-dxgkddi_setupprioritybands.md).

## -struct-fields

### -field gracePeriodForBand

Grace period, in 100ns units when preempting another priority band for this priority band. This value is ignored for IDLE band, since it never preempts other bands. For realtime band this will be typically set to 0, because realtime processes need to use the GPU right away.

### -field processQuantumForBand

Default quantum in 100ns units for scheduling across processes within a priority band.

### -field processGracePeriodForBand

Default grace period in 100ns units for processes that preempt each other within a priority band.

### -field targetNormalBandPercentage

For normal priority band, specifies the target GPU percentage in situations when it's starved by the focus band. Valid values are between 0 and 50, with the default value on desktop systems being 10.



## -see-also

[DxgkddiSetupPriorityBands](nc-d3dkmddi-dxgkddi_setupprioritybands.md)
