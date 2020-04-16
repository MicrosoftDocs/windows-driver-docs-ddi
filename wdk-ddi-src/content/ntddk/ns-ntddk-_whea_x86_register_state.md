---
UID: NS:ntddk._WHEA_X86_REGISTER_STATE
title: _WHEA_X86_REGISTER_STATE (ntddk.h)
description: The WHEA_X86_REGISTER_STATE structure describes the state of an x86 processor's registers.
old-location: whea\whea_x86_register_state.htm
tech.root: whea
ms.assetid: 64079b03-9771-4940-a19e-a29389cbf2fe
ms.date: 02/20/2018
keywords: ["_WHEA_X86_REGISTER_STATE structure"]
ms.keywords: "*PWHEA_X86_REGISTER_STATE, PWHEA_X86_REGISTER_STATE, PWHEA_X86_REGISTER_STATE structure pointer [WHEA Drivers and Applications], WHEA_X86_REGISTER_STATE, WHEA_X86_REGISTER_STATE structure [WHEA Drivers and Applications], _WHEA_X86_REGISTER_STATE, ntddk/PWHEA_X86_REGISTER_STATE, ntddk/WHEA_X86_REGISTER_STATE, whea.whea_x86_register_state, whearef_330404b2-bd6e-4220-97c6-8bacc803eb78.xml"
f1_keywords:
 - "ntddk/WHEA_X86_REGISTER_STATE"
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
- WHEA_X86_REGISTER_STATE
product:
- Windows
targetos: Windows
req.typenames: WHEA_X86_REGISTER_STATE, *PWHEA_X86_REGISTER_STATE
---

# _WHEA_X86_REGISTER_STATE structure


## -description


The WHEA_X86_REGISTER_STATE structure describes the state of an x86 processor's registers.


## -struct-fields




### -field Eax

The accumulator register.


### -field Ebx

The base register.


### -field Ecx

The count register.


### -field Edx

The data register.


### -field Esi

The source index register.


### -field Edi

The destination index register.


### -field Ebp

The base pointer register.


### -field Esp

The stack pointer register.


### -field Cs

The code segment register.


### -field Ds

The data segment register.


### -field Ss

The stack segment register.


### -field Es

The extra segment register.


### -field Fs

The general purpose segment register FS.


### -field Gs

The general purpose segment register GS.


### -field Eflags

The flags register.


### -field Eip

The instruction pointer register.


### -field Cr0

The control register 0.


### -field Cr1

The control register 1.


### -field Cr2

The control register 2.


### -field Cr3

The control register 3.


### -field Cr4

The control register 4.


### -field Gdtr

The global descriptor table register.


### -field Idtr

The interrupt descriptor table register.


### -field Ldtr

The local descriptor table register.


### -field Tr

The task register.


## -remarks



If the <b>RegisterContextType</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_xpf_context_info">WHEA_XPF_CONTEXT_INFO</a> structure is set to XPF_CONTEXT_INFO_32BITCONTEXT, the <b>RegisterData</b> member of that structure contains a WHEA_X86_REGISTER_STATE structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_xpf_context_info">WHEA_XPF_CONTEXT_INFO</a>
 

 

