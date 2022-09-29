---
UID: NF:wudfddi.IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled
title: IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled (wudfddi.h)
description: A driver's OnD0ExitPreInterruptsDisabled event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.
old-location: wdf\ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled.htm
tech.root: wdf
ms.date: 08/11/2022
keywords: ["IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled"]
ms.keywords: IPnpCallbackHardwareInterrupt interface,OnD0ExitPreInterruptsDisabled method, IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled, IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled, OnD0ExitPreInterruptsDisabled, OnD0ExitPreInterruptsDisabled method, OnD0ExitPreInterruptsDisabled method,IPnpCallbackHardwareInterrupt interface, umdf.ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled, wdf.ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled, wudfddi/IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled
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
 - IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled
 - wudfddi/IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled
---

# IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

A driver's **OnD0ExitPreInterruptsDisabled** event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.

## -parameters

### -param pDevice

A pointer to an [IWDFDevice3](/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3) interface.

### -param TargetState [in]

A [WDF_POWER_DEVICE_STATE](/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state) enumerator value that identifies the target device power state that the device is about to enter.

## -returns

If successful, **OnD0ExitPreInterruptsDisabled**, returns S_OK. Otherwise, it returns an appropriate failure status.

## -see-also

- [Enabling and Disabling Interrupts](/windows-hardware/drivers/wdf/enabling-and-disabling-interrupts)
- [IPnpCallbackHardwareInterrupt](/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardwareinterrupt)
- [OnD0EntryPostInterruptsEnabled](/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0entrypostinterruptsenabled)
