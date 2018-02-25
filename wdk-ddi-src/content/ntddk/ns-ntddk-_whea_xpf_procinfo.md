---
UID: NS:ntddk._WHEA_XPF_PROCINFO
title: "_WHEA_XPF_PROCINFO"
author: windows-driver-content
description: The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.
old-location: whea\whea_xpf_procinfo.htm
old-project: whea
ms.assetid: 90fb54dd-a2df-423c-8dd6-bd99c5ad1de4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , *, *PWHEA_XPF_PROCINFO, ,, A, C, E, F, H, I, N, O, P, PWHEA_XPF_PROCINFO, PWHEA_XPF_PROCINFO structure pointer [WHEA Drivers and Applications], R, W, WHEA_XPF_PROCINFO, WHEA_XPF_PROCINFO structure [WHEA Drivers and Applications], X, _, _WHEA_XPF_PROCINFO, ntddk/PWHEA_XPF_PROCINFO, ntddk/WHEA_XPF_PROCINFO, whea.whea_xpf_procinfo, whearef_adb42f7c-687b-47ef-b3fe-312ef995e5c5.xml"
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
-	WHEA_XPF_PROCINFO
product: Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCINFO, *PWHEA_XPF_PROCINFO
---

# _WHEA_XPF_PROCINFO structure


## -description


The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.


## -syntax


````
typedef struct _WHEA_XPF_PROCINFO {
  GUID                        CheckInfoId;
  WHEA_XPF_PROCINFO_VALIDBITS ValidBits;
  union {
    WHEA_XPF_CACHE_CHECK CacheCheck;
    WHEA_XPF_TLB_CHECK   TlbCheck;
    WHEA_XPF_BUS_CHECK   BusCheck;
    WHEA_XPF_MS_CHECK    MsCheck;
    ULONGLONG            AsULONGLONG;
  } CheckInfo;
  ULONGLONG                   TargetId;
  ULONGLONG                   RequesterId;
  ULONGLONG                   ResponderId;
  ULONGLONG                   InstructionPointer;
} WHEA_XPF_PROCINFO, *PWHEA_XPF_PROCINFO;
````


## -struct-fields




### -field CheckInfoId

A GUID that identifies the processor error information that is contained in the <b>CheckInfo</b> member. The following are the possible GUIDs that can be specified for this member:





#### WHEA_CACHECHECK_GUID

The <b>CheckInfo.CacheCheck</b> member contains cache error information.



#### WHEA_TLBCHECK_GUID

The <b>CheckInfo.TlbCheck</b> member contains translation lookaside buffer error information.



#### WHEA_BUSCHECK_GUID

The <b>CheckInfo.BusCheck</b> member contains bus error information.



#### WHEA_MSCHECK_GUID

The <b>CheckInfo.MsCheck</b> member contains microarchitecture-specific error information.


### -field ValidBits

A <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo_validbits.md">WHEA_XPF_PROCINFO_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field CheckInfo

A union of unions that are specific to each different type of processor error information.

This member contains valid data only if the <b>ValidBits.CheckInfo</b> bit is set.





#### CacheCheck

A <a href="..\ntddk\ns-ntddk-_whea_xpf_cache_check.md">WHEA_XPF_CACHE_CHECK</a> union that describes cache error information. 



#### TlbCheck

A <a href="..\ntddk\ns-ntddk-_whea_xpf_tlb_check.md">WHEA_XPF_TLB_CHECK</a> union that describes translation lookaside buffer error information. 



#### BusCheck

A <a href="..\ntddk\ns-ntddk-_whea_xpf_bus_check.md">WHEA_XPF_BUS_CHECK</a> union that describes bus error information.



#### MsCheck

A <a href="..\ntddk\ns-ntddk-_whea_xpf_ms_check.md">WHEA_XPF_MS_CHECK</a> union that describes microarchitecture-specific error information. 



#### AsULONGLONG

A ULONGLONG representation of the contents of the <b>CheckInfo</b> union.


### -field TargetId

An identifier that uniquely identifies the target associated with the error.

This member contains valid data only if the <b>ValidBits.TargetId</b> bit is set.


### -field RequesterId

An identifier that uniquely identifies the requester associated with the error.

This member contains valid data only if the <b>ValidBits.RequesterId</b> bit is set.


### -field ResponderId

An identifier that uniquely identifies the responder associated with the error.

This member contains valid data only if the <b>ValidBits.Responder</b> bit is set.


### -field InstructionPointer

The instruction pointer at the time that the error occurred.

This member contains valid data only if the <b>ValidBits.InstructionPointer</b> bit is set.


## -remarks



The <a href="..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contains an array of WHEA_XPF_PROCINFO structures, each of which describes specific error information associated with the processor error that occurred.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_xpf_tlb_check.md">WHEA_XPF_TLB_CHECK</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_bus_check.md">WHEA_XPF_BUS_CHECK</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_ms_check.md">WHEA_XPF_MS_CHECK</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_cache_check.md">WHEA_XPF_CACHE_CHECK</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo_validbits.md">WHEA_XPF_PROCINFO_VALIDBITS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCINFO structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

