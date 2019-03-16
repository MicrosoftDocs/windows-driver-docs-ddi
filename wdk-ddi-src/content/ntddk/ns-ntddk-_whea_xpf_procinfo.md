---
UID: NS:ntddk._WHEA_XPF_PROCINFO
title: _WHEA_XPF_PROCINFO (ntddk.h)
description: The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.
old-location: whea\whea_xpf_procinfo.htm
tech.root: whea
ms.assetid: 90fb54dd-a2df-423c-8dd6-bd99c5ad1de4
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_PROCINFO, PWHEA_XPF_PROCINFO, PWHEA_XPF_PROCINFO structure pointer [WHEA Drivers and Applications], WHEA_XPF_PROCINFO, WHEA_XPF_PROCINFO structure [WHEA Drivers and Applications], _WHEA_XPF_PROCINFO, ntddk/PWHEA_XPF_PROCINFO, ntddk/WHEA_XPF_PROCINFO, whea.whea_xpf_procinfo, whearef_adb42f7c-687b-47ef-b3fe-312ef995e5c5.xml"
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
- WHEA_XPF_PROCINFO
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCINFO, *PWHEA_XPF_PROCINFO
---

# _WHEA_XPF_PROCINFO structure


## -description


The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.


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

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560663">WHEA_XPF_PROCINFO_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field CheckInfo

A union of unions that are specific to each different type of processor error information.

This member contains valid data only if the <b>ValidBits.CheckInfo</b> bit is set.




### -field CheckInfo.CacheCheck

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560642">WHEA_XPF_CACHE_CHECK</a> union that describes cache error information. 


### -field CheckInfo.TlbCheck

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560665">WHEA_XPF_TLB_CHECK</a> union that describes translation lookaside buffer error information. 


### -field CheckInfo.BusCheck

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560639">WHEA_XPF_BUS_CHECK</a> union that describes bus error information.


### -field CheckInfo.MsCheck

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560652">WHEA_XPF_MS_CHECK</a> union that describes microarchitecture-specific error information. 


### -field CheckInfo.AsULONGLONG

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



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560655">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contains an array of WHEA_XPF_PROCINFO structures, each of which describes specific error information associated with the processor error that occurred.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560639">WHEA_XPF_BUS_CHECK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560642">WHEA_XPF_CACHE_CHECK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560652">WHEA_XPF_MS_CHECK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560655">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560663">WHEA_XPF_PROCINFO_VALIDBITS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560665">WHEA_XPF_TLB_CHECK</a>
 

 

