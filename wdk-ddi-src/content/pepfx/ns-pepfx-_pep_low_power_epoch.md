---
UID: NS:pepfx._PEP_LOW_POWER_EPOCH
title: _PEP_LOW_POWER_EPOCH (pepfx.h)
description: The PEP_LOW_POWER_EPOCH structure is used to provide data for a PEP_DPM_LOW_POWER_EPOCH notification (deprecated).
old-location: kernel\pep_low_power_epoch.htm
tech.root: kernel
ms.assetid: 730312DE-5F11-46C8-8298-55AA5756C995
ms.date: 04/30/2018
keywords: ["PEP_LOW_POWER_EPOCH structure"]
ms.keywords: "*PPEP_LOW_POWER_EPOCH, PEP_LOW_POWER_EPOCH, PEP_LOW_POWER_EPOCH structure [Kernel-Mode Driver Architecture], PPEP_LOW_POWER_EPOCH, PPEP_LOW_POWER_EPOCH structure pointer [Kernel-Mode Driver Architecture], _PEP_LOW_POWER_EPOCH, kernel.pep_low_power_epoch, pepfx/PEP_LOW_POWER_EPOCH, pepfx/PPEP_LOW_POWER_EPOCH"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
targetos: Windows
req.typenames: PEP_LOW_POWER_EPOCH, *PPEP_LOW_POWER_EPOCH
f1_keywords:
 - _PEP_LOW_POWER_EPOCH
 - pepfx/_PEP_LOW_POWER_EPOCH
 - PPEP_LOW_POWER_EPOCH
 - pepfx/PPEP_LOW_POWER_EPOCH
 - PEP_LOW_POWER_EPOCH
 - pepfx/PEP_LOW_POWER_EPOCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_LOW_POWER_EPOCH
---

# _PEP_LOW_POWER_EPOCH structure


## -description

The <b>PEP_LOW_POWER_EPOCH</b> structure is used to provide data for a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_low_power_epoch">PEP_DPM_LOW_POWER_EPOCH</a> notification (deprecated).

## -struct-fields

### -field LowPowerEpoch

When <b>TRUE</b>, indicates that the low power epoch is on.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_low_power_epoch">PEP_DPM_LOW_POWER_EPOCH notification</a>

