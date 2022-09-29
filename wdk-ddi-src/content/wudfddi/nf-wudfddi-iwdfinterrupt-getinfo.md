---
UID: NF:wudfddi.IWDFInterrupt.GetInfo
title: IWDFInterrupt::GetInfo (wudfddi.h)
description: The GetInfo method retrieves information about a specified interrupt.
old-location: wdf\iwdfinterrupt_getinfo.htm
tech.root: wdf
ms.date: 08/11/2022
keywords: ["IWDFInterrupt::GetInfo"]
ms.keywords: GetInfo, GetInfo method, GetInfo method,IWDFInterrupt interface, IWDFInterrupt interface,GetInfo method, IWDFInterrupt.GetInfo, IWDFInterrupt::GetInfo, umdf.iwdfinterrupt_getinfo, wdf.iwdfinterrupt_getinfo, wudfddi/IWDFInterrupt::GetInfo
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFInterrupt::GetInfo
 - wudfddi/IWDFInterrupt::GetInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFInterrupt::GetInfo
---

# IWDFInterrupt::GetInfo

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **GetInfo** method retrieves information about a specified interrupt.

## -parameters

### -param InterruptInfo

A pointer to a caller-allocated [WDF_INTERRUPT_INFO](../wudfinterrupt/ns-wudfinterrupt-_wdf_interrupt_info.md) structure that the driver has previously initialized by calling [WDF_INTERRUPT_INFO_INIT](../wudfinterrupt/nf-wudfinterrupt-wdf_interrupt_info_init.md).

## -remarks

The **GetInfo** method can obtain interrupt information only if your driver calls it after the framework has called the driver's [OnPrepareHardware](./nf-wudfddi-ipnpcallbackhardware2-onpreparehardware.md) callback function and before the framework has called the driver's [OnReleaseHardware](./nf-wudfddi-ipnpcallbackhardware2-onreleasehardware.md) callback function.

For information about the order in which a driver's callback functions are called, see [PnP and Power Management Scenarios in UMDF](/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios-in-umdf).

For more information about handling interrupts in UMDF drivers, see [Accessing Hardware and Handling Interrupts](/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts).

### Examples

``` cpp
IWDFInterrupt* pInterrupt;
WDF_INTERRUPT_INFO  Info;

WDF_INTERRUPT_INFO_INIT(&Info);
pInterrupt->GetInfo(&Info);
```

## -see-also

- [IWDFInterrupt](./nn-wudfddi-iwdfinterrupt.md)
- [OnPrepareHardware](./nf-wudfddi-ipnpcallbackhardware2-onpreparehardware.md)
- [OnReleaseHardware](./nf-wudfddi-ipnpcallbackhardware2-onreleasehardware.md)
- [WDF_INTERRUPT_INFO](../wudfinterrupt/ns-wudfinterrupt-_wdf_interrupt_info.md)
- [WDF_INTERRUPT_INFO_INIT](../wudfinterrupt/nf-wudfinterrupt-wdf_interrupt_info_init.md)
