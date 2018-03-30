---
UID: NS:wudfinterrupt._WDF_INTERRUPT_INFO
title: "_WDF_INTERRUPT_INFO"
author: windows-driver-content
description: The WDF_INTERRUPT_INFO structure contains information about a device's interrupt resource.
old-location: wdf\wdf_interrupt_info_umdf.htm
old-project: wdf
ms.assetid: 37B997D1-6F5D-4685-BF46-2C33685C157F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_INTERRUPT_INFO, PWDF_INTERRUPT_INFO, PWDF_INTERRUPT_INFO structure pointer, WDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO structure, _WDF_INTERRUPT_INFO, umdf.wdf_interrupt_info, wdf.wdf_interrupt_info_umdf, wudfinterrupt/PWDF_INTERRUPT_INFO, wudfinterrupt/WDF_INTERRUPT_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	WDF_INTERRUPT_INFO
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_INFO structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure contains information about a device's interrupt resource.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Reserved1

This member is reserved for future use. 


### -field TargetProcessorSet

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed value that specifies the interrupt's processor affinity.


### -field Reserved2

This member is reserved for future use. 


### -field MessageNumber

If the <b>MessageSignaled</b> member is TRUE, this is the interrupt's message number.


### -field Vector

The interrupt vector.


### -field Irql

The DIRQL at which the device interrupts.


### -field Mode

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a>-typed enumerator that indicates whether the interrupt is level-triggered or edge-triggered. The KINTERRUPT_MODE enumeration type is defined in Wudfwdm.h.


### -field Polarity

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh464028">WDF_INTERRUPT_POLARITY</a>-typed enumerator that identifies the interrupt signal's polarity.


### -field MessageSignaled

A Boolean value that, if TRUE, indicates that the interrupt is message-signaled. If FALSE, the interrupt is not message-signaled.


### -field ShareDisposition

A CM_SHARE_DISPOSITION-typed enumerator that indicates whether the interrupt is being shared. The value is <b>CmResourceShareShared</b> if the interrupt is being shared or <b>CmResourceShareDeviceExclusive</b> if the interrupt is not being shared. The CM_SHARE_DISPOSITION enumeration type is defined in Wudfwdm.h.


### -field Group

A value that identifies the processor group that the <b>TargetProcessorSet</b> member applies to. This value is zero if the computer has only one processor group or if the operating system does not support processor groups. The <b>Group</b> member is available in version 1.9 and later versions of KMDF.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure is used as input to the <a href="https://msdn.microsoft.com/744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F">IWDFInterrupt::GetInfo</a> method. To initialize a <b>WDF_INTERRUPT_INFO</b> structure, your driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a> before calling <b>IWDFInterrupt::GetInfo</b>.




## -see-also




<a href="https://msdn.microsoft.com/744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F">IWDFInterrupt::GetInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464028">WDF_INTERRUPT_POLARITY</a>
 

 

