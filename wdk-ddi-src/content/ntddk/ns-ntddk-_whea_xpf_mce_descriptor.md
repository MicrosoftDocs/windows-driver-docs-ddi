---
UID: NS:ntddk._WHEA_XPF_MCE_DESCRIPTOR
title: _WHEA_XPF_MCE_DESCRIPTOR (ntddk.h)
description: The WHEA_XPF_MCE_DESCRIPTOR structure describes a machine check exception (MCE) error source for an x86 or x64 processor.
old-location: whea\whea_xpf_mce_descriptor.htm
tech.root: whea
ms.assetid: cdf52fe7-40ac-4baf-aaa0-c23b40574376
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_MCE_DESCRIPTOR, PWHEA_XPF_MCE_DESCRIPTOR, PWHEA_XPF_MCE_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_XPF_MCE_DESCRIPTOR, WHEA_XPF_MCE_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_XPF_MCE_DESCRIPTOR, ntddk/PWHEA_XPF_MCE_DESCRIPTOR, ntddk/WHEA_XPF_MCE_DESCRIPTOR, whea.whea_xpf_mce_descriptor, whearef_77725c63-dffe-45f9-9a52-cef3fb8d124e.xml"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_XPF_MCE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_MCE_DESCRIPTOR, *PWHEA_XPF_MCE_DESCRIPTOR
---

# _WHEA_XPF_MCE_DESCRIPTOR structure


## -description


The WHEA_XPF_MCE_DESCRIPTOR structure describes a machine check exception (MCE) error source for an x86 or x64 processor.


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_XPFMCE.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field NumberOfBanks

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560651">WHEA_XPF_MC_BANK_DESCRIPTOR</a> structures contained in the <b>Banks</b> member.


### -field Flags

An XPF_MCE_FLAGS union that indicates which of the members of the WHEA_XPF_MCE_DESCRIPTOR structure can be written to by the operating system. The XPF_MCE_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _XPF_MCE_FLAGS {
  struct {
    UCHAR  MCG_CapabilityRW:1;
    UCHAR  MCG_GlobalControlRW:1;
    UCHAR  Reserved:30;
  };
  UCHAR  AsULONG;
} XPF_MCE_FLAGS, *PXPF_MCE_FLAGS;</pre>
</td>
</tr>
</table></span></div>




#### MCG_CapabilityRW

A single bit that indicates that the operating system can write to the <b>MCG_Capability</b> member of the WHEA_XPF_MCE_DESCRIPTOR structure.



#### MCG_GlobalControlRW

A single bit that indicates that the operating system can write to the <b>MCG_GlobalControl</b> member of the WHEA_XPF_MCE_DESCRIPTOR structure.



#### Reserved

Reserved for system use.



#### AsULONG

A ULONG representation of the contents of the XPF_MCE_FLAGS union.


### -field MCG_Capability

The contents of the processor's IA32_MCG_CAP model-specific register. This register contains capability information about the machine check architecture of the processor. For more information about the IA32_MCG_CAP register, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.


### -field MCG_GlobalControl

The contents of the processor's IA32_MCG_CTL model-specific register. This register controls the reporting of machine check exceptions. For more information about the IA32_MCG_CTL register, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.


### -field Banks

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560651">WHEA_XPF_MC_BANK_DESCRIPTOR</a> structures that describe the banks of machine check registers.


## -remarks



A WHEA_XPF_MCE_DESCRIPTOR structure is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560651">WHEA_XPF_MC_BANK_DESCRIPTOR</a>
 

 

