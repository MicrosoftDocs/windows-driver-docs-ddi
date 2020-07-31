---
UID: NF:wudfddi.IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled
title: IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled (wudfddi.h)
description: A driver's OnD0ExitPreInterruptsDisabled event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.
old-location: wdf\ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled.htm
tech.root: wdf
ms.assetid: C67EA467-D344-44D0-93E8-29D29A3A586B
ms.date: 02/26/2018
keywords: ["IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled"]
ms.keywords: IPnpCallbackHardwareInterrupt interface,OnD0ExitPreInterruptsDisabled method, IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled, IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled, OnD0ExitPreInterruptsDisabled, OnD0ExitPreInterruptsDisabled method, OnD0ExitPreInterruptsDisabled method,IPnpCallbackHardwareInterrupt interface, umdf.ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled, wdf.ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled, wudfddi/IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled
f1_keywords:
 - "wudfddi/IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled"
 - "IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled
targetos: Windows
req.typenames: 
---

# IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnD0ExitPreInterruptsDisabled</b> event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.


## -parameters




### -param pDevice




### -param TargetState [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the target device power state that the device is about to enter.


#### - pInterrupt [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface.


## -returns



If successful, <b>OnD0ExitPreInterruptsDisabled</b>, returns S_OK. Otherwise, it returns an appropriate failure status.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enabling-and-disabling-interrupts">Enabling and Disabling Interrupts</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardwareinterrupt">IPnpCallbackHardwareInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0entrypostinterruptsenabled">OnD0EntryPostInterruptsEnabled</a>
 

 

