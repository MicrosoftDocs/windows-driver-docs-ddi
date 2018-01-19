---
UID: NC:pepfx.POFXCALLBACKREQUESTINTERRUPT
title: POFXCALLBACKREQUESTINTERRUPT
author: windows-driver-content
description: The RequestInterrupt routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state.
old-location: kernel\requestinterrupt.htm
old-project: kernel
ms.assetid: B999405D-D6A5-4DFF-A902-F9C938C29063
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _VPCI_PNP_ID, VPCI_PNP_ID, *PVPCI_PNP_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RequestInterrupt
req.alt-loc: pepfx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= HIGH_LEVEL
req.typenames: VPCI_PNP_ID, *PVPCI_PNP_ID
---

# POFXCALLBACKREQUESTINTERRUPT callback



## -description
The <b>RequestInterrupt</b> routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state.



## -prototype

````
POFXCALLBACKREQUESTINTERRUPT RequestInterrupt;

NTSTATUS RequestInterrupt(
  _In_ ULONG Gsiv
)
{ ... }
````


## -parameters

### -param Gsiv [in]

The global system interrupt vector (GSIV) number that identifies this interrupt. The ACPI firmware assigns GSIV numbers to all primary interrupt lines. For secondary (GPIO) interrupt lines, the GSIV number is dynamically assigned by the operating system.


## -returns
<b>RequestInterrupt</b> returns STATUS_SUCCESS if the specified interrupt is successfully replayed. Possible error return values include the following status code.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Not a valid GSIV number.

 


## -remarks
This routine is implemented by the power management framework (PoFx) and is called by the platform extension plug-in (PEP). The <b>RequestInterrupt</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>RequestInterrupt</b> routine.

Assertion of an edge-triggered interrupt signal is transient in nature and can be lost if the power to a primary interrupt controller is gated off when the interrupt occurs. In contrast, a level-triggered interrupt signal is expected to remain asserted until it can be serviced.

A PEP can call this routine at IRQL &lt;= HIGH_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKREQUESTINTERRUPT routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

