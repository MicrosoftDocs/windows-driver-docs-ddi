---
UID: NF:wdm.PoFxCompleteDirectedPowerDown
title: PoFxCompleteDirectedPowerDown function
author: windows-driver-content
description: A Directed Power Framework (DFx) client driver calls this function to complete the Directed power down transition.
tech.root: 
ms.assetid: c4ce7279-b8d7-4215-a9d2-e09b73d3ecfd
ms.author: windowsdriverdev
ms.date: 08/19/2019
keywords: ["PoFxCompleteDirectedPowerDown function"]
ms.keywords: PoFxCompleteDirectedPowerDown
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - PoFxCompleteDirectedPowerDown
 - wdm/PoFxCompleteDirectedPowerDown
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - PoFxCompleteDirectedPowerDown
product:
 - Windows
---

# PoFxCompleteDirectedPowerDown function


## -description

A DFx (Directed [PoFx](https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework)) client driver calls this function to complete the Directed power down transition.

## -parameters

### -param Handle

A POHANDLE value that represents the registration of the processor (as a device) with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

## -remarks

The driver typically calls this routine from its [*PO_FX_DIRECTED_POWER_DOWN_CALLBACK*](nc-wdm-po_fx_directed_power_down_callback.md) callback routine.

## -see-also

https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework

