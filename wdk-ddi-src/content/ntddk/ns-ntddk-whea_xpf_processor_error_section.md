---
UID: NS:ntddk.WHEA_XPF_PROCESSOR_ERROR_SECTION
title: WHEA_XPF_PROCESSOR_ERROR_SECTION
author: windows-driver-content
description: The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture.
old-location: whea\whea_xpf_processor_error_section.htm
tech.root: whea
ms.assetid: e994c778-4a1b-4c7d-a9fb-4481d9edda0d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: whea.whea_xpf_processor_error_section, WHEA_XPF_PROCESSOR_ERROR, whearef_e3338334-dc16-4242-9c30-0daaab2df957.xml, WHEA_XPF_PROCESSOR_ERROR_SECTION, WHEA_XPF_PROCESSOR_ERROR_SECTION structure [WHEA Drivers and Applications], *PWHEA_XPF_PROCESSOR_ERROR, PWHEA_XPF_PROCESSOR_ERROR_SECTION structure pointer [WHEA Drivers and Applications], ntddk/WHEA_XPF_PROCESSOR_ERROR_SECTION, ntddk/PWHEA_XPF_PROCESSOR_ERROR_SECTION, PWHEA_XPF_PROCESSOR_ERROR_SECTION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_XPF_PROCESSOR_ERROR_SECTION
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCESSOR_ERROR, *PWHEA_XPF_PROCESSOR_ERROR
---

# WHEA_XPF_PROCESSOR_ERROR_SECTION structure


## -description


The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture.


## -syntax


```
typedef struct _WHEA_XPF_PROCESSOR_ERROR_SECTION {
  WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS ValidBits;
  ULONGLONG                                  LocalAPICId;
  UCHAR                                      CpuId[48];
  UCHAR                                      VariableInfo[ANYSIZE_ARRAY];
} WHEA_XPF_PROCESSOR_ERROR_SECTION, *PWHEA_XPF_PROCESSOR_ERROR_SECTION;
```


## -struct-fields





#### - ValidBits

A <a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section_validbits.md">WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data and the number of structures that are contained in the <b>VariableInfo</b> member.


#### - LocalAPICId

The value programmed into the local APIC ID register.

This member contains valid data only if the <b>ValidBits.LocalAPICId</b> bit is set.


#### - CpuId

A 48-byte buffer that contains the results of executing the CPUID instruction. For more information about the CPUID instruction, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.

This member contains valid data only if the <b>ValidBits.CpuId </b>bit is set.


#### - VariableInfo

A variable length buffer that contains zero or more <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structures followed by zero or more <a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a> structures. The number of WHEA_XPF_PROCINFO structures is specified in <b>ValidBits.ProcInfoCount</b>. The number of WHEA_XPF_CONTEXT_INFO structures is specified in <b>ValidBits.ContextInfoCount</b>. For a diagram that shows how these data structures are stored in the buffer, see the Remarks section.


## -remarks


The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes the error data that is contained in an x86/x64 processor error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains an x86/x64 processor error section only if the <b>SectionType </b>member of one of the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describes the error record sections for that error record contains XPF_PROCESSOR_ERROR_SECTION_GUID.

The following diagram shows how the data structures that contain the processor error data are stored in the <b>VariableInfo</b> member.
<img alt="Diagram illustrating how the data structures that contain the processor error data are stored in the VariableInfo member" src="images/wheaxpfsection.gif"/>


## -see-also

<a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section_validbits.md">WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS</a>

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>

<a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a>

<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a>

 

 


