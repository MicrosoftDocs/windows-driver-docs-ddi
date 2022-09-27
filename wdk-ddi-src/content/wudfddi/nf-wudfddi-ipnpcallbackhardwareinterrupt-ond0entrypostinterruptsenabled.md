---
UID: NF:wudfddi.IPnpCallbackHardwareInterrupt.OnD0EntryPostInterruptsEnabled
title: IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled (wudfddi.h)
description: A driver's OnD0EntryPostInterruptsEnabled event callback function performs device-specific operations that are required when the driver enables the device's hardware interrupts.
old-location: wdf\ipnpcallbackhardwareinterrupt_ond0entrypostinterruptsenabled.htm
tech.root: wdf
ms.date: 08/11/2022
keywords: ["IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled"]
ms.keywords: IPnpCallbackHardwareInterrupt interface,OnD0EntryPostInterruptsEnabled method, IPnpCallbackHardwareInterrupt.OnD0EntryPostInterruptsEnabled, IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled, OnD0EntryPostInterruptsEnabled, OnD0EntryPostInterruptsEnabled method, OnD0EntryPostInterruptsEnabled method,IPnpCallbackHardwareInterrupt interface, umdf.ipnpcallbackhardwareinterrupt_ond0entrypostinterruptsenabled, wdf.ipnpcallbackhardwareinterrupt_ond0entrypostinterruptsenabled, wudfddi/IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
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
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
 - wudfddi/IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
---

# IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

A driver's **OnD0EntryPostInterruptsEnabled** event callback function performs device-specific operations that are required when the driver enables the device's hardware interrupts.

## -parameters

### -param pDevice

A pointer to [IWDFDevice3](./nn-wudfddi-iwdfdevice3.md) interface.

### -param PreviousState [in]

A [WDF_POWER_DEVICE_STATE](../wdfdevice/ne-wdfdevice-_wdf_power_device_state.md) enumerator value that identifies the previous device power state.

## -returns

If successful, **OnD0EntryPostInterruptsEnabled** returns S_OK. Otherwise, it returns an appropriate failure status.

## -see-also

- [IPnpCallbackHardwareInterrupt](./nn-wudfddi-ipnpcallbackhardwareinterrupt.md)
- [OnD0ExitPreInterruptsDisabled](./nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0exitpreinterruptsdisabled.md)
- [Enabling and Disabling Interrupts](/windows-hardware/drivers/wdf/enabling-and-disabling-interrupts)