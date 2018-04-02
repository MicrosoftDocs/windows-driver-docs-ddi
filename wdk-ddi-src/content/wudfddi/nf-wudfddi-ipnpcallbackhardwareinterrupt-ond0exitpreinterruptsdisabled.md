---
UID: NF:wudfddi.IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled
title: IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled method
author: windows-driver-content
description: A driver's OnD0ExitPreInterruptsDisabled event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.
old-location: wdf\ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled.htm
old-project: wdf
ms.assetid: C67EA467-D344-44D0-93E8-29D29A3A586B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallbackHardwareInterrupt, IPnpCallbackHardwareInterrupt interface, OnD0ExitPreInterruptsDisabled method, IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled, OnD0ExitPreInterruptsDisabled method, OnD0ExitPreInterruptsDisabled method, IPnpCallbackHardwareInterrupt interface, OnD0ExitPreInterruptsDisabled,IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled, umdf.ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled, wdf.ipnpcallbackhardwareinterrupt_ond0exitpreinterruptsdisabled, wudfddi/IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IPnpCallbackHardwareInterrupt.OnD0ExitPreInterruptsDisabled
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackHardwareInterrupt::OnD0ExitPreInterruptsDisabled method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnD0ExitPreInterruptsDisabled</b> event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.


## -parameters




### -param pDevice




### -param TargetState [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552421">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the target device power state that the device is about to enter.


#### - pInterrupt [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451197">IWDFDevice3</a> interface.


## -returns



If successful, <b>OnD0ExitPreInterruptsDisabled</b>, returns S_OK. Otherwise, it returns an appropriate failure status.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/432907e7-05a3-4a99-a291-33bd1eefa94c">Enabling and Disabling Interrupts</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439744">IPnpCallbackHardwareInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439750">OnD0EntryPostInterruptsEnabled</a>
 

 

