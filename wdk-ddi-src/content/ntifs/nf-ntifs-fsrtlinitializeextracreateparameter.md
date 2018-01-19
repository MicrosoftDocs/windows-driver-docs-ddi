---
UID: NF:ntifs.FsRtlInitializeExtraCreateParameter
title: FsRtlInitializeExtraCreateParameter function
author: windows-driver-content
description: The FsRtlInitializeExtraCreateParameter routine initializes an extra create parameter (ECP) context structure.
old-location: ifsk\fsrtlinitializeextracreateparameter.htm
old-project: ifsk
ms.assetid: e3be12e4-84f3-4bd5-af9a-26ad89948e50
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlInitializeExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitializeExtraCreateParameter routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlInitializeExtraCreateParameter
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlInitializeExtraCreateParameter function



## -description
The <b>FsRtlInitializeExtraCreateParameter</b> routine initializes an extra create parameter (ECP) context structure. 



## -syntax

````
VOID FsRtlInitializeExtraCreateParameter(
  _In_     PECP_HEADER                                    Ecp,
  _In_     ULONG                                          EcpFlags,
  _In_opt_ PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK CleanupCallback,
  _In_     ULONG                                          TotalSize,
  _In_     LPCGUID                                        EcpType,
  _In_opt_ PVOID                                          ListAllocatedFrom
);
````


## -parameters

### -param Ecp [in]

Pointer to the ECP context structure to initialize. 


### -param EcpFlags [in]

Defines initialization options. Currently, no flags are defined. 


### -param CleanupCallback [in, optional]

Optional pointer to a filter-defined cleanup callback routine of type <a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>. The cleanup callback routine is called when the ECP context structure (created by the <a href="..\ntifs\nf-ntifs-fsrtlallocateextracreateparameter.md">FsRtlAllocateExtraCreateParameter</a> routine) is deleted. Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable. 


### -param TotalSize [in]

The size, in bytes, of the ECP context structure to initialize. 


### -param EcpType [in]

Pointer to a GUID that indicates the type of ECP for which the context structure will be initialized. For more information about ECPs, see <a href="https://msdn.microsoft.com/e32aeec6-1a0a-4d21-8358-89d9fc0a15eb">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>. 


### -param ListAllocatedFrom [in, optional]

Optional pointer to the list from which the ECP context structure is allocated. 


## -returns
None


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlallocateextracreateparameter.md">FsRtlAllocateExtraCreateParameter</a>
</dt>
<dt>
<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitializeExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

