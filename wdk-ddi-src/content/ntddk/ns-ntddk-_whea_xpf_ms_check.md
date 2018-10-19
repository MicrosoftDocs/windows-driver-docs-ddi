---
UID: NS:ntddk._WHEA_XPF_MS_CHECK
title: "_WHEA_XPF_MS_CHECK"
author: windows-driver-content
description: The WHEA_XPF_MS_CHECK union describes microarchitecture-specific error information for an x86 or x64 processor.
old-location: whea\whea_xpf_ms_check.htm
tech.root: whea
ms.assetid: aa446b31-ac53-4623-bacd-72ab72e94618
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_MS_CHECK, PWHEA_XPF_MS_CHECK, PWHEA_XPF_MS_CHECK union pointer [WHEA Drivers and Applications], WHEA_XPF_MS_CHECK, WHEA_XPF_MS_CHECK union [WHEA Drivers and Applications], _WHEA_XPF_MS_CHECK, ntddk/PWHEA_XPF_MS_CHECK, ntddk/WHEA_XPF_MS_CHECK, whea.whea_xpf_ms_check, whearef_ebbe0f28-499b-41ad-9e2b-c533c391c154.xml"
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
-	WHEA_XPF_MS_CHECK
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_MS_CHECK, *PWHEA_XPF_MS_CHECK
---

# _WHEA_XPF_MS_CHECK structure


## -description


The WHEA_XPF_MS_CHECK union describes microarchitecture-specific error information for an x86 or x64 processor.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.ErrorTypeValid

A single bit that indicates that the <b>ErrorType</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ProcessorContextCorruptValid

A single bit that indicates that the <b>ProcessorContextCorrupt</b> member contains valid data.


### -field DUMMYSTRUCTNAME.UncorrectedValid

A single bit that indicates that the <b>Uncorrected</b> member contains valid data.


### -field DUMMYSTRUCTNAME.PreciseIPValid

A single bit that indicates that the <b>PreciseIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.RestartableIPValid

A single bit that indicates that the <b>RestartableIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.OverflowValid

A single bit that indicates that the <b>Overflow</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ReservedValue

 


### -field DUMMYSTRUCTNAME.ErrorType

The type of error that occurred. Possible values are:



All other values are processor-specific.

This member contains valid data only if the <b>ErrorTypeValid</b> bit is set.


### -field DUMMYSTRUCTNAME.ProcessorContextCorrupt

A single bit that indicates that the processor context might have been corrupted.

This member contains valid data only if the <b>ProcessorContextCorruptValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Uncorrected

A single bit that indicates that the error has not been corrected.

This member contains valid data only if the <b>UncorrectedValid</b> bit is set.


### -field DUMMYSTRUCTNAME.PreciseIP

A single bit that indicates that the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> structure that contains this WHEA_XPF_MS_CHECK union is directly associated with the error.

This member contains valid data only if the <b>PreciseIPValid </b>bit is set.


### -field DUMMYSTRUCTNAME.RestartableIP

A single bit that indicates that program execution can be restarted reliably at the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> union that contains this WHEA_XPF_MS_CHECK structure.

This member contains valid data only if the <b>RestartableIPValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Overflow

A single bit that indicates that an error overflow occurred.

This member contains valid data only if the <b>OverflowValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field XpfMsCheck

A ULONGLONG representation of the contents of the WHEA_XPF_MS_CHECK union.


##### - ErrorType.XPF_MS_CHECK_ERRORTYPE_EXTERNAL

An external error.


##### - ErrorType.XPF_MS_CHECK_ERRORTYPE_FRC

A functional redundancy checking (FRC) error.


##### - ErrorType.XPF_MS_CHECK_ERRORTYPE_INTERNALUNCLASSIFIED

An unclassified internal error.


##### - ErrorType.XPF_MS_CHECK_ERRORTYPE_MCROMPARITY

A microcode ROM parity error.


##### - ErrorType.XPF_MS_CHECK_ERRORTYPE_NOERROR

No error occurred.


##### - ErrorType.XPF_MS_CHECK_ERRORTYPE_UNCLASSIFIED

An unclassified error.


#### - ReservedValid

Reserved for system use.


## -remarks



If the <b>CheckInfoId</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> structure contains WHEA_MSCHECK_GUID, the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains a WHEA_XPF_MS_CHECK union.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a>
 

 

