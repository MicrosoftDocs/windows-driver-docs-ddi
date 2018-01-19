---
UID: NS:ntddk._WHEA_XPF_MS_CHECK
title: _WHEA_XPF_MS_CHECK
author: windows-driver-content
description: The WHEA_XPF_MS_CHECK union describes microarchitecture-specific error information for an x86 or x64 processor.
old-location: whea\whea_xpf_ms_check.htm
old-project: whea
ms.assetid: aa446b31-ac53-4623-bacd-72ab72e94618
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_XPF_MS_CHECK, WHEA_XPF_MS_CHECK, *PWHEA_XPF_MS_CHECK
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
req.alt-api: WHEA_XPF_MS_CHECK
req.alt-loc: ntddk.h
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
req.typenames: WHEA_XPF_MS_CHECK, *PWHEA_XPF_MS_CHECK
---

# _WHEA_XPF_MS_CHECK structure



## -description
The WHEA_XPF_MS_CHECK union describes microarchitecture-specific error information for an x86 or x64 processor.



## -syntax

````
typedef union _WHEA_XPF_MS_CHECK {
  struct {
    ULONGLONG ErrorTypeValid  :1;
    ULONGLONG ProcessorContextCorruptValid  :1;
    ULONGLONG UncorrectedValid  :1;
    ULONGLONG PreciseIPValid  :1;
    ULONGLONG RestartableIPValid  :1;
    ULONGLONG OverflowValid  :1;
    ULONGLONG ReservedValid  :10;
    ULONGLONG ErrorType  :3;
    ULONGLONG ProcessorContextCorrupt  :1;
    ULONGLONG Uncorrected  :1;
    ULONGLONG PreciseIP  :1;
    ULONGLONG RestartableIP  :1;
    ULONGLONG Overflow  :1;
    ULONGLONG Reserved  :40;
  };
  ULONGLONG XpfMsCheck;
} WHEA_XPF_MS_CHECK, *PWHEA_XPF_MS_CHECK;
````


## -struct-fields

### -field ErrorTypeValid

A single bit that indicates that the <b>ErrorType</b> member contains valid data.


### -field ProcessorContextCorruptValid

A single bit that indicates that the <b>ProcessorContextCorrupt</b> member contains valid data.


### -field UncorrectedValid

A single bit that indicates that the <b>Uncorrected</b> member contains valid data.


### -field PreciseIPValid

A single bit that indicates that the <b>PreciseIP</b> member contains valid data.


### -field RestartableIPValid

A single bit that indicates that the <b>RestartableIP</b> member contains valid data.


### -field OverflowValid

A single bit that indicates that the <b>Overflow</b> member contains valid data.


### -field ReservedValid

Reserved for system use.


### -field ErrorType

The type of error that occurred. Possible values are:




### -field XPF_MS_CHECK_ERRORTYPE_NOERROR

No error occurred.


### -field XPF_MS_CHECK_ERRORTYPE_UNCLASSIFIED

An unclassified error.


### -field XPF_MS_CHECK_ERRORTYPE_MCROMPARITY

A microcode ROM parity error.


### -field XPF_MS_CHECK_ERRORTYPE_EXTERNAL

An external error.


### -field XPF_MS_CHECK_ERRORTYPE_FRC

A functional redundancy checking (FRC) error.


### -field XPF_MS_CHECK_ERRORTYPE_INTERNALUNCLASSIFIED

An unclassified internal error.

</dd>
</dl>
All other values are processor-specific.

This member contains valid data only if the <b>ErrorTypeValid</b> bit is set.


### -field ProcessorContextCorrupt

A single bit that indicates that the processor context might have been corrupted.

This member contains valid data only if the <b>ProcessorContextCorruptValid</b> bit is set.


### -field Uncorrected

A single bit that indicates that the error has not been corrected.

This member contains valid data only if the <b>UncorrectedValid</b> bit is set.


### -field PreciseIP

A single bit that indicates that the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structure that contains this WHEA_XPF_MS_CHECK union is directly associated with the error.

This member contains valid data only if the <b>PreciseIPValid </b>bit is set.


### -field RestartableIP

A single bit that indicates that program execution can be restarted reliably at the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> union that contains this WHEA_XPF_MS_CHECK structure.

This member contains valid data only if the <b>RestartableIPValid</b> bit is set.


### -field Overflow

A single bit that indicates that an error overflow occurred.

This member contains valid data only if the <b>OverflowValid</b> bit is set.


### -field Reserved

Reserved for system use.


### -field XpfMsCheck

A ULONGLONG representation of the contents of the WHEA_XPF_MS_CHECK union.


## -remarks
If the <b>CheckInfoId</b> member of a <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structure contains WHEA_MSCHECK_GUID, the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains a WHEA_XPF_MS_CHECK union.


## -see-also
<dl>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_MS_CHECK union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

