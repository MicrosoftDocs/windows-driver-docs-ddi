---
UID: NS:ntddk.WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
title: WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS (ntddk.h)
description: The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_XPF_PROCESSOR_ERROR_SECTION structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's VariableInfo member.
old-location: whea\whea_xpf_processor_error_section_validbits.htm
tech.root: whea
ms.assetid: f6b18ffa-f784-4382-9861-4d92e2071ebf
ms.date: 12/14/2017
ms.keywords: PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, whearef_cd965099-c110-4ff6-993e-c4ccab88cd80.xml, ntddk/WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], whea.whea_xpf_processor_error_section_validbits, WHEA_XPF_PROCESSOR_ERROR_VALIDBITS, WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], *PWHEA_XPF_PROCESSOR_ERROR_VALIDBITS
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
-	WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCESSOR_ERROR_VALIDBITS, *PWHEA_XPF_PROCESSOR_ERROR_VALIDBITS
---

# WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.


## -syntax


```cpp
typedef union _WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS {
  struct {
    ULONGLONG LocalAPICId  :1;
    ULONGLONG CpuId  :1;
    ULONGLONG ProcInfoCount  :6;
    ULONGLONG ContextInfoCount  :6;
    ULONGLONG Reserved  :50;
  };
  ULONGLONG ValidBits;
} WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, *PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS;
```


## -struct-fields





#### - LocalAPICId

A single bit that indicates that the <b>LocalAPICId</b> member of the WHEA_XPF_PROCESSOR_ERROR_SECTION structure contains valid data.


#### - CpuId

A single bit that indicates that the <b>CpuId</b> member of the WHEA_XPF_PROCESSOR_ERROR_SECTION structure contains valid data.


#### - ProcInfoCount

The number of <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.


#### - ContextInfoCount

The number of <a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a> structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.


#### - Reserved

Reserved for system use.


#### - ValidBits

A ULONGLONG representation of the contents of the WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union.


## -remarks


A WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a>

<a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>

<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a>

 

 


