---
UID: NS:ntddk._WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
title: _WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS (ntddk.h)
description: The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_XPF_PROCESSOR_ERROR_SECTION structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's VariableInfo member.
old-location: whea\whea_xpf_processor_error_section_validbits.htm
tech.root: whea
ms.assetid: f6b18ffa-f784-4382-9861-4d92e2071ebf
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], _WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, ntddk/WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, whea.whea_xpf_processor_error_section_validbits, whearef_cd965099-c110-4ff6-993e-c4ccab88cd80.xml"
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
- WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, *PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
---

# _WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a [WHEA_XPF_PROCESSOR_ERROR_SECTION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_processor_error_section) structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.LocalAPICId

A single bit that indicates that the <b>LocalAPICId</b> member of the WHEA_XPF_PROCESSOR_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.CpuId

A single bit that indicates that the <b>CpuId</b> member of the WHEA_XPF_PROCESSOR_ERROR_SECTION structure contains valid data.


### -field DUMMYSTRUCTNAME.ProcInfoCount

The number of [WHEA_XPF_PROCINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_procinfo) structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.


### -field DUMMYSTRUCTNAME.ContextInfoCount

The number of [WHEA_XPF_CONTEXT_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_context_info) structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union.


## -remarks



A WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union is contained within the [WHEA_XPF_PROCESSOR_ERROR_SECTION]([WHEA_XPF_PROCESSOR_ERROR_SECTION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_processor_error_section) structure.




## -see-also




- [WHEA_XPF_CONTEXT_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_context_info)
- [WHEA_XPF_PROCESSOR_ERROR_SECTION]([WHEA_XPF_PROCESSOR_ERROR_SECTION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_processor_error_section)
- [WHEA_XPF_PROCINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_procinfo) 
 

 

