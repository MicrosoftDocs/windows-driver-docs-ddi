---
UID: NS:ntddk._WHEA_XPF_CONTEXT_INFO
title: "_WHEA_XPF_CONTEXT_INFO"
author: windows-driver-content
description: The WHEA_XPF_CONTEXT_INFO structure describes processor context information for an x86 or x64 processor.
old-location: whea\whea_xpf_context_info.htm
old-project: whea
ms.assetid: 044af92b-b77c-415c-9ca5-4436bfe497e5
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_WHEA_XPF_CONTEXT_INFO, ntddk/WHEA_XPF_CONTEXT_INFO, PWHEA_XPF_CONTEXT_INFO structure pointer [WHEA Drivers and Applications], whea.whea_xpf_context_info, whearef_3e1bae81-9b21-4b0c-bd86-b957afb95713.xml, WHEA_XPF_CONTEXT_INFO structure [WHEA Drivers and Applications], WHEA_XPF_CONTEXT_INFO, ntddk/PWHEA_XPF_CONTEXT_INFO, PWHEA_XPF_CONTEXT_INFO, *PWHEA_XPF_CONTEXT_INFO"
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
-	WHEA_XPF_CONTEXT_INFO
product: Windows
targetos: Windows
req.typenames: "*PWHEA_XPF_CONTEXT_INFO, WHEA_XPF_CONTEXT_INFO"
---

# _WHEA_XPF_CONTEXT_INFO structure


## -description


The WHEA_XPF_CONTEXT_INFO structure describes processor context information for an x86 or x64 processor.


## -syntax


````
typedef struct _WHEA_XPF_CONTEXT_INFO {
  USHORT    RegisterContextType;
  USHORT    RegisterDataSize;
  ULONG     MSRAddress;
  ULONGLONG MmRegisterAddress;
  UCHAR     RegisterData[1];
} WHEA_XPF_CONTEXT_INFO, *PWHEA_XPF_CONTEXT_INFO;
````


## -struct-fields




### -field RegisterContextType

The type of processor context information described by the structure. Possible values are:





#### XPF_CONTEXT_INFO_UNCLASSIFIEDDATA

Unclassified processor context data.



#### XPF_CONTEXT_INFO_MSRREGISTERS

Machine check and other machine-specific registers.



#### XPF_CONTEXT_INFO_32BITCONTEXT

32-bit execution context registers.



#### XPF_CONTEXT_INFO_64BITCONTEXT

64-bit execution context registers.



#### XPF_CONTEXT_INFO_FXSAVE

Floating point registers as saved by the FXSAVE instruction. For more information about the FXSAVE instruction, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.



#### XPF_CONTEXT_INFO_32BITDEBUGREGS

32-bit debug registers.



#### XPF_CONTEXT_INFO_64BITDEBUGREGS

64-bit debug registers.



#### XPF_CONTEXT_INFO_MMREGISTERS

Memory mapped registers.


### -field RegisterDataSize

The size, in bytes, of the register data that is contained in the <b>RegisterData</b> member.


### -field MSRAddress

The starting address of the machine-specific registers. This member contains valid data only if the <b>RegisterContextType</b> member is set to either XPF_CONTEXT_INFO_UNCLASSIFIEDDATA or XPF_CONTEXT_INFO_MSRREGISTERS. For all other types of processor context information, this member should contain zero.


### -field MmRegisterAddress

The starting memory address of the memory mapped registers. This member contains valid data only if the <b>RegisterContextType</b> member is set to XPF_CONTEXT_INFO_MMREGISTERS. For all other types of processor context information, this member should contain zero.


#### - RegisterData

A variable length buffer that contains register data or raw data. The contents of the buffer depends upon the type of processor context information that is specified in the RegisterContextType member as follows:






#### XPF_CONTEXT_INFO_UNCLASSIFIEDDATA

The buffer contains raw unformatted data. The number of bytes of data is specified in the RegisterDataSize member. 





#### XPF_CONTEXT_INFO_MSRREGISTERS

The buffer contains an array of 64-bit machine check and other machine-specific registers. The number of registers in the array is determined by dividing the size specified in the RegisterDataSize member by eight. 





#### XPF_CONTEXT_INFO_32BITCONTEXT

The buffer contains a WHEA_X86_REGISTER_STATE structure.



#### XPF_CONTEXT_INFO_64BITCONTEXT

The buffer contains a WHEA_X64_REGISTER_STATE structure.



#### XPF_CONTEXT_INFO_FXSAVE

The buffer contains the floating point registers as saved by the FXSAVE instruction. For more information about the FXSAVE instruction, see the  <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>. 





#### XPF_CONTEXT_INFO_32BITDEBUGREGS

The buffer contains an array of eight 64-bit values that contain the 32-bit debug registers DR0-DR7. Each of the 32-bit debug registers are zero-extended to 64-bits.



#### XPF_CONTEXT_INFO_64BITDEBUGREGS

The buffer contains an array of eight 64-bit values that contain the 64-bit debug registers DR0-DR7.



#### XPF_CONTEXT_INFO_MMREGISTERS

The buffer contains an array of 64-bit memory mapped registers. The number of registers in the array is determined by dividing the size specified in the RegisterDataSize member by eight.


## -remarks



The <b>VariableInfo</b> member of the <a href="..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contains zero or more WHEA_XPF_CONTEXT_INFO structures, each of which describes specific context information associated with the processor error that occurred. If the size of a particular WHEA_XPF_CONTEXT_INFO structure is not an even multiple of 16 bytes, the space that is allocated for the structure in the buffer will be padded with additional bytes that are set to zero to round the allocated space up to an even multiple of 16 bytes.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_x86_register_state.md">WHEA_X86_REGISTER_STATE</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_x64_register_state.md">WHEA_X64_REGISTER_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_CONTEXT_INFO structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

