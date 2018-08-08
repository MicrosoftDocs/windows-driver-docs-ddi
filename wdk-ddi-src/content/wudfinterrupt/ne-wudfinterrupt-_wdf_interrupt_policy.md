---
UID: NE:wudfinterrupt._WDF_INTERRUPT_POLICY
title: "_WDF_INTERRUPT_POLICY"
author: windows-driver-content
description: The WDF_INTERRUPT_POLICY enumeration type identifies the affinity policies that the Plug and Play (PnP) manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.
old-location: wdf\wdf_interrupt_policy_umdf.htm
tech.root: wdf
ms.assetid: 92E2A992-8A0B-4E0F-B615-DC6E30E4A227
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_INTERRUPT_POLICY, PWDF_INTERRUPT_POLICY, PWDF_INTERRUPT_POLICY enumeration pointer, WDF_INTERRUPT_POLICY, WDF_INTERRUPT_POLICY enumeration, WdfIrqPolicyAllCloseProcessors, WdfIrqPolicyAllProcessorsInMachine, WdfIrqPolicyMachineDefault, WdfIrqPolicyOneCloseProcessor, WdfIrqPolicySpecifiedProcessors, WdfIrqPolicySpreadMessagesAcrossAllProcessors, _WDF_INTERRUPT_POLICY, umdf.wdf_interrupt_policy, wdf.wdf_interrupt_policy_umdf, wudfinterrupt/PWDF_INTERRUPT_POLICY, wudfinterrupt/WDF_INTERRUPT_POLICY, wudfinterrupt/WdfIrqPolicyAllCloseProcessors, wudfinterrupt/WdfIrqPolicyAllProcessorsInMachine, wudfinterrupt/WdfIrqPolicyMachineDefault, wudfinterrupt/WdfIrqPolicyOneCloseProcessor, wudfinterrupt/WdfIrqPolicySpecifiedProcessors, wudfinterrupt/WdfIrqPolicySpreadMessagesAcrossAllProcessors"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Windows
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
-	HeaderDef
api_location:
-	Wudfinterrupt.h
api_name:
-	WDF_INTERRUPT_POLICY
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLICY, *PWDF_INTERRUPT_POLICY
---

# _WDF_INTERRUPT_POLICY enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464032">WDF_INTERRUPT_POLICY</a> enumeration type identifies the affinity policies that the Plug and Play (PnP) manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.


## -enum-fields




### -field WdfIrqPolicyMachineDefault

Use the system's default affinity policy.


### -field WdfIrqPolicyAllCloseProcessors

For NUMA systems, the PnP manager should assign the device's interrupts to processors that are close to the device. For non-NUMA systems, specifying <b>WdfIrqPolicyAllCloseProcessors</b> is the same as specifying <b>WdfIrqPolicyAllProcessorsInMachine</b>.


### -field WdfIrqPolicyOneCloseProcessor

For NUMA systems, the PnP manager should assign one interrupt to a processor that is close to the device. For non-NUMA systems, the PnP manager can assign the interrupt to any processor.


### -field WdfIrqPolicyAllProcessorsInMachine

The PnP manager can assign a device's interrupts to any of the system's processors.


### -field WdfIrqPolicySpecifiedProcessors

The PnP manager should assign the device's interrupts only to specified processors.


### -field WdfIrqPolicySpreadMessagesAcrossAllProcessors

The PnP manager should assign different message-based interrupts to different processors, if possible. 


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464032">WDF_INTERRUPT_POLICY</a> enumeration type is used as input to the <a href="https://msdn.microsoft.com/EDBCBB37-41A4-4234-BE8C-4C8739BC287B">IWDFInterrupt::SetPolicy</a> method.




## -see-also




<a href="https://msdn.microsoft.com/EDBCBB37-41A4-4234-BE8C-4C8739BC287B">IWDFInterrupt::SetPolicy</a>
 

 

