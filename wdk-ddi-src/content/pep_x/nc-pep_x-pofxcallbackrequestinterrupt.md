---
UID: NC:pep_x.POFXCALLBACKREQUESTINTERRUPT
title: POFXCALLBACKREQUESTINTERRUPT
author: windows-driver-content
description: The RequestInterrupt routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state.
old-location: kernel\requestinterrupt.htm
old-project: kernel
ms.assetid: B999405D-D6A5-4DFF-A902-F9C938C29063
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: POFXCALLBACKREQUESTINTERRUPT, RequestInterrupt, RequestInterrupt routine [Kernel-Mode Driver Architecture], kernel.requestinterrupt, pepfx/RequestInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= HIGH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	RequestInterrupt
product: Windows
targetos: Windows
req.typenames: PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE
---

# POFXCALLBACKREQUESTINTERRUPT callback


## -description


The <b>RequestInterrupt</b> routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state.


## -parameters




### -param Gsiv [in]

The global system interrupt vector (GSIV) number that identifies this interrupt. The ACPI firmware assigns GSIV numbers to all primary interrupt lines. For secondary (GPIO) interrupt lines, the GSIV number is dynamically assigned by the operating system.


## -returns



<b>RequestInterrupt</b> returns STATUS_SUCCESS if the specified interrupt is successfully replayed. Possible error return values include the following status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Not a valid GSIV number.

</td>
</tr>
</table>
 




## -remarks



This routine is implemented by the power management framework (PoFx) and is called by the platform extension plug-in (PEP). The <b>RequestInterrupt</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>RequestInterrupt</b> routine.

Assertion of an edge-triggered interrupt signal is transient in nature and can be lost if the power to a primary interrupt controller is gated off when the interrupt occurs. In contrast, a level-triggered interrupt signal is expected to remain asserted until it can be serviced.

A PEP can call this routine at IRQL &lt;= HIGH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
 

 

