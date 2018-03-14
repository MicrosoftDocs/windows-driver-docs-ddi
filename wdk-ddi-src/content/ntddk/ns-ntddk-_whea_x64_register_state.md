---
UID: NS:ntddk._WHEA_X64_REGISTER_STATE
title: "_WHEA_X64_REGISTER_STATE"
author: windows-driver-content
description: The WHEA_X64_REGISTER_STATE structure describes the state of an x64 processor's registers.
old-location: whea\whea_x64_register_state.htm
old-project: whea
ms.assetid: 690c900f-fba8-4712-9a05-bfbe633dd9cf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_X64_REGISTER_STATE, PWHEA_X64_REGISTER_STATE, PWHEA_X64_REGISTER_STATE structure pointer [WHEA Drivers and Applications], WHEA_X64_REGISTER_STATE, WHEA_X64_REGISTER_STATE structure [WHEA Drivers and Applications], _WHEA_X64_REGISTER_STATE, ntddk/PWHEA_X64_REGISTER_STATE, ntddk/WHEA_X64_REGISTER_STATE, whea.whea_x64_register_state, whearef_2602d89a-de68-4dd9-ba4b-bb42fc0f258b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_X64_REGISTER_STATE
product: Windows
targetos: Windows
req.typenames: WHEA_X64_REGISTER_STATE, *PWHEA_X64_REGISTER_STATE
---

# _WHEA_X64_REGISTER_STATE structure


## -description


The WHEA_X64_REGISTER_STATE structure describes the state of an x64 processor's registers.


## -syntax


````
typedef struct _WHEA_X64_REGISTER_STATE {
  ULONGLONG Rax;
  ULONGLONG Rbx;
  ULONGLONG Rcx;
  ULONGLONG Rdx;
  ULONGLONG Rsi;
  ULONGLONG Rdi;
  ULONGLONG Rbp;
  ULONGLONG Rsp;
  ULONGLONG R8;
  ULONGLONG R9;
  ULONGLONG R10;
  ULONGLONG R11;
  ULONGLONG R12;
  ULONGLONG R13;
  ULONGLONG R14;
  ULONGLONG R15;
  USHORT    Cs;
  USHORT    Ds;
  USHORT    Ss;
  USHORT    Es;
  USHORT    Fs;
  USHORT    Gs;
  ULONG     Reserved;
  ULONGLONG Rflags;
  ULONGLONG Eip;
  ULONGLONG Cr0;
  ULONGLONG Cr1;
  ULONGLONG Cr2;
  ULONGLONG Cr3;
  ULONGLONG Cr4;
  ULONGLONG Cr8;
  WHEA128A  Gdtr;
  WHEA128A  Idtr;
  USHORT    Ldtr;
  USHORT    Tr;
} WHEA_X64_REGISTER_STATE, *PWHEA_X64_REGISTER_STATE;
````


## -struct-fields




### -field Rax

The accumulator register.


### -field Rbx

The base register.


### -field Rcx

The count register.


### -field Rdx

The data register.


### -field Rsi

The source index register.


### -field Rdi

The destination index register.


### -field Rbp

The base pointer register.


### -field Rsp

The stack pointer register.


### -field R8

The general purpose register R8.


### -field R9

The general purpose register R9.


### -field R10

The general purpose register R10.


### -field R11

The general purpose register R11.


### -field R12

The general purpose register R12.


### -field R13

The general purpose register R13.


### -field R14

The general purpose register R14.


### -field R15

The general purpose register R15.


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


### -field Reserved

Reserved for system use.


### -field Rflags

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


### -field Cr8

The control register 8.


### -field Gdtr

A WHEA128A structure that contains the state of the global descriptor table register. The WHEA128A structure describes a 128-bit value and is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _WHEA128A {
  ULONGLONG  Low;
  LONGLONG  High;
} WHEA128A, *PWHEA128A;</pre>
</td>
</tr>
</table></span></div>




#### Low

The low order 64 bits of the 128-bit value.



#### High

The high order 64 bits of the 128-bit value.


### -field Idtr

A WHEA128A structure that contains the state of the interrupt descriptor table register. For a description of the WHEA128A structure, see the description for the <b>Gdtr</b> member.


### -field Ldtr

The local descriptor table register.


### -field Tr

The task register.


## -remarks



If the <b>RegisterContextType</b> member of a <a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a> structure is set to XPF_CONTEXT_INFO_64BITCONTEXT, the <b>RegisterData</b> member of that structure contains a WHEA_X64_REGISTER_STATE structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a>



 

 


