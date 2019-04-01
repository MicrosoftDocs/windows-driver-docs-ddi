---
UID: NF:wdm.PoFxCompleteDirectedPowerDown
title: PoFxCompleteDirectedPowerDown function
author: windows-driver-content
description: TBD
tech.root:
ms.assetid: c4ce7279-b8d7-4215-a9d2-e09b73d3ecfd
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
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
topic_type: 
- apiref
api_type: 
- 
api_location: 
- 
api_name: 
- PoFxCompleteDirectedPowerDown
product: 
- Windows
targetos: Windows

---

# PoFxCompleteDirectedPowerDown function


## -description

A DFx (Directed [PoFx](https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework)) client driver calls this function to complete the Directed power down transition.

## -parameters

### -param Handle

A POHANDLE value that represents the registration of the processor (as a device) with <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).


## -returns

This function returns VOID.

## -remarks

The driver typically calls this routine from its [*PO_FX_DIRECTED_POWER_DOWN_CALLBACK*](nc-wdm-po_fx_directed_power_down_callback.md) callback routine.

## -see-also

https://review.docs.microsoft.com/en-us/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework?branch=kernel_19h1