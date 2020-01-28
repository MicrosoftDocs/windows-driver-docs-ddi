---
UID: NE:wudfddi.__MIDL___MIDL_itf_wudfddi_0000_0000_0001
title: __MIDL___MIDL_itf_wudfddi_0000_0000_0001 (wudfddi.h)
description: The POWER_ACTION enumeration identifies the system power actions that can occur on a computer.
old-location: wdf\power_action.htm
tech.root: wdf
ms.assetid: 0c4a5eb8-d364-4e5d-9d2f-2605c8c34f63
ms.date: 02/26/2018
ms.keywords: "*PPOWER_ACTION, POWER_ACTION, POWER_ACTION enumeration, PPOWER_ACTION, PPOWER_ACTION enumeration pointer, PowerActionHibernate, PowerActionNone, PowerActionReserved, PowerActionShutdown, PowerActionShutdownOff, PowerActionShutdownReset, PowerActionSleep, PowerActionWarmEject, __MIDL___MIDL_itf_wudfddi_0000_0000_0001, umdf.power_action, umdfstructs_02db2a83-1907-4aa2-9cdd-af3477e78ddd.xml, wdf.power_action, wudfddi/POWER_ACTION, wudfddi/PPOWER_ACTION, wudfddi/PowerActionHibernate, wudfddi/PowerActionNone, wudfddi/PowerActionReserved, wudfddi/PowerActionShutdown, wudfddi/PowerActionShutdownOff, wudfddi/PowerActionShutdownReset, wudfddi/PowerActionSleep, wudfddi/PowerActionWarmEject"
f1_keywords:
 - "wudfddi/POWER_ACTION"
req.header: wudfddi.h
req.include-header: Wudfddi.h, Ntpoapi.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
- HeaderDef
api_location:
- Wudfddi.h
api_name:
- POWER_ACTION
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
---

# __MIDL___MIDL_itf_wudfddi_0000_0000_0001 enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>POWER_ACTION</b> enumeration identifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-actions">system power actions</a> that can occur on a computer.


## -enum-fields




### -field PowerActionNone

No power action is taking place.


### -field PowerActionReserved

Reserved for system use.


### -field PowerActionSleep

The computer is entering a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-sleeping-states">system sleeping (S1, S2, or S3) state</a>.


### -field PowerActionHibernate

The computer is entering its <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-sleeping-states">hibernation (S4) state</a>.


### -field PowerActionShutdown

The computer is entering its <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-shutdown-state-s5">shutdown (S5) state</a>. After all devices have entered their <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-sleeping-states">off (D3) state</a>, the computer remains powered on until an administrator presses the power button.


### -field PowerActionShutdownReset

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off and then immediately restarts and returns to its working (S0) state.


### -field PowerActionShutdownOff

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off.


### -field PowerActionWarmEject

The computer is being ejected from an ACPI-compatible dock device. Typically, the computer's power state does not change.


## -remarks



The <b>POWER_ACTION</b> enumeration is used as the return value for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-getsystempoweraction">IWDFDevice2::GetSystemPowerAction</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-getsystempoweraction">IWDFDevice2::GetSystemPowerAction</a>
 

 

