---
UID: NS:ntddk._WHEA_XPF_MC_BANK_DESCRIPTOR
title: _WHEA_XPF_MC_BANK_DESCRIPTOR (ntddk.h)
description: The WHEA_XPF_MC_BANK_DESCRIPTOR structure describes a bank of machine check registers for an x86 or x64 processor.
old-location: whea\whea_xpf_mc_bank_descriptor.htm
tech.root: whea
ms.assetid: e5360f75-53cf-4025-9a1c-665c098329dd
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_MC_BANK_DESCRIPTOR, PWHEA_XPF_MC_BANK_DESCRIPTOR, PWHEA_XPF_MC_BANK_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_XPF_MC_BANK_DESCRIPTOR, WHEA_XPF_MC_BANK_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_XPF_MC_BANK_DESCRIPTOR, ntddk/PWHEA_XPF_MC_BANK_DESCRIPTOR, ntddk/WHEA_XPF_MC_BANK_DESCRIPTOR, whea.whea_xpf_mc_bank_descriptor, whearef_9f1970bd-6dbf-4104-9525-2018ab2f766e.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_XPF_MC_BANK_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_MC_BANK_DESCRIPTOR, *PWHEA_XPF_MC_BANK_DESCRIPTOR
---

# _WHEA_XPF_MC_BANK_DESCRIPTOR structure


## -description


The WHEA_XPF_MC_BANK_DESCRIPTOR structure describes a bank of machine check registers for an x86 or x64 processor.


## -struct-fields




### -field BankNumber

The processor machine check register bank number.


### -field ClearOnInitialization

A Boolean value that indicates that the status registers for the bank are to be cleared by the operating system during initialization.


### -field StatusDataFormat

The format of the data in the register bank's status register. Possible values are:





#### WHEA_XPF_MC_BANK_STATUSFORMAT_IA32MCA

IA32 machine check architecture.



#### WHEA_XPF_MC_BANK_STATUSFORMAT_Intel64MCA

Intel64 machine check architecture.



#### WHEA_XPF_MC_BANK_STATUSFORMAT_AMD64MCA

AMD64 machine check architecture.


### -field Flags

An XPF_MC_BANK_FLAGS union that indicates which of the members of the WHEA_XPF_MC_BANK_DESCRIPTOR structure can be written to by the operating system. The XPF_MC_BANK_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _XPF_MC_BANK_FLAGS {
  struct {
    UCHAR  ClearOnInitializationRW:1;
    UCHAR  ControlDataRW:1;
    UCHAR  Reserved:6;
  };
  UCHAR  AsUCHAR;
} XPF_MC_BANK_FLAGS, *PXPF_MC_BANK_FLAGS;</pre>
</td>
</tr>
</table></span></div>




#### ClearOnInitializationRW

A single bit that indicates that the operating system can write to the <b>ClearOnInitialization</b> member of the WHEA_XPF_MC_BANK_DESCRIPTOR structure.



#### ControlDataRW

A single bit that indicates that the operating system can write to the <b>ControlData</b> member of the WHEA_XPF_MC_BANK_DESCRIPTOR structure.



#### Reserved

Reserved for system use.



#### AsUCHAR

A UCHAR representation of contents of the XPF_MC_BANK_FLAGS union.


### -field ControlMsr

The model-specific register address of the register bank's IA32_MCi_CTL register. For more information about the IA32_MCi_CTL register, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.


### -field StatusMsr

The model-specific register address of the register bank's IA32_MCi_STATUS register. For more information about the IA32_MCi_STATUS register, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.


### -field AddressMsr

The model-specific register address of the register bank's IA32_MCi_ADDR register. For more information about the IA32_MCi_ADDR register, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.


### -field MiscMsr

The model-specific register address of the register bank's IA32_MCi_MISC register. For more information about the IA32_MCi_MISC register, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.


### -field ControlData

The value that the operating system writes to the register bank's control register during initialization.


## -remarks



An array of WHEA_XPF_MC_BANK_DESCRIPTOR structures is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_cmc_descriptor">WHEA_XPF_CMC_DESCRIPTOR</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_mce_descriptor">WHEA_XPF_MCE_DESCRIPTOR</a> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_cmc_descriptor">WHEA_XPF_CMC_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_mce_descriptor">WHEA_XPF_MCE_DESCRIPTOR</a>
 

 

