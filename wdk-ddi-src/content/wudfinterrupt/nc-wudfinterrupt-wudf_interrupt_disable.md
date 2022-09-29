---
UID: NC:wudfinterrupt.WUDF_INTERRUPT_DISABLE
title: WUDF_INTERRUPT_DISABLE (wudfinterrupt.h)
description: A driver's OnInterruptDisable event callback function disables a specified hardware interrupt.
old-location: wdf\oninterruptdisable.htm
tech.root: wdf
ms.date: 08/12/2022
keywords: ["WUDF_INTERRUPT_DISABLE callback function"]
ms.keywords: OnInterruptDisable, OnInterruptDisable callback function, WUDF_INTERRUPT_DISABLE, WUDF_INTERRUPT_DISABLE callback, umdf.oninterruptdisable, wdf.oninterruptdisable, wudfinterrupt/OnInterruptDisable
req.header: wudfinterrupt.h
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
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - WUDF_INTERRUPT_DISABLE
 - wudfinterrupt/WUDF_INTERRUPT_DISABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wudfinterrupt.h
api_name:
 - WUDF_INTERRUPT_DISABLE
---

# WUDF_INTERRUPT_DISABLE callback function

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

A driver's *OnInterruptDisable* event callback function disables a specified hardware interrupt.

## -parameters

### -param Interrupt [in]

A pointer to the [IWDFInterrupt](../wudfddi/nn-wudfddi-iwdfinterrupt.md) interface.

### -param AssociatedDevice [in]

A pointer to the [IWDFDevice](../wudfddi/nn-wudfddi-iwdfdevice.md) interface that the driver used to call [CreateInterrupt](../wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt.md).

## -returns

*OnInterruptDisable*  must return S_OK if the operation succeeds. Otherwise, the callback should return one of the error codes that are defined in Winerror.h.

## -remarks

To register an *OnInterruptDisable* callback function, your driver must place the callback function's address in a [WUDF_INTERRUPT_CONFIG](./ns-wudfinterrupt-_wudf_interrupt_config.md) structure before calling [IWDFDevice::CreateInterrupt](../wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt.md).

The framework calls the driver's *OnInterruptDisable* callback function each time the device leaves its working (D0) state. Additionally, a driver can cause the framework to call the *OnInterruptDisable* callback function by calling [IWDFInterrupt::Disable](../wudfddi/nf-wudfddi-iwdfinterrupt-disable.md).

Before calling the *OnInterruptDisable* callback function, the framework calls the driver's [OnD0ExitPreInterruptsDisabled](../wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0exitpreinterruptsdisabled.md) event callback function and acquires the user-mode interrupt lock.

For more information about handling interrupts in UMDF drivers, see [Accessing Hardware and Handling Interrupts](/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts).

### Examples

The function type is declared in *Wudfinterrupt.h*, as follows.

```cpp
typedef
__drv_functionClass(WUDF_INTERRUPT_DISABLE)
HRESULT
WUDF_INTERRUPT_DISABLE(
    _In_
    IWDFInterrupt* Interrupt,
    _In_
    IWDFDevice* AssociatedDevice
    );

typedef WUDF_INTERRUPT_DISABLE *PFN_WUDF_INTERRUPT_DISABLE;
```

To define an *OnInterruptDisable* callback function that is named *MyInterruptDisable*, you must first provide a function declaration that SDV and other verification tools require, as follows:

```cpp
WUDF_INTERRUPT_DISABLE  MyInterruptDisable;
```

Then, implement your callback function as follows:

```cpp
HRESULT
  MyInterruptDisable (
    IN IWDFInterrupt* pInterrupt,
    IN IWDFDevice*  pAssociatedDevice
    )
  {…}

```

## -see-also

- [IWDFDevice::CreateInterrupt](../wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt.md)
- [OnInterruptEnable](./nc-wudfinterrupt-wudf_interrupt_enable.md)
- [WUDF_INTERRUPT_CONFIG](./ns-wudfinterrupt-_wudf_interrupt_config.md)
