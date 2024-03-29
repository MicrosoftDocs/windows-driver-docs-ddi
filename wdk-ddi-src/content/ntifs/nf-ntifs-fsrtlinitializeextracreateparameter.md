---
UID: NF:ntifs.FsRtlInitializeExtraCreateParameter
title: FsRtlInitializeExtraCreateParameter function (ntifs.h)
description: The FsRtlInitializeExtraCreateParameter routine initializes an extra create parameter (ECP) context structure.
old-location: ifsk\fsrtlinitializeextracreateparameter.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlInitializeExtraCreateParameter function"]
ms.keywords: FsRtlInitializeExtraCreateParameter, FsRtlInitializeExtraCreateParameter routine [Installable File System Drivers], fsrtlref_266d4d18-e024-42e8-8ca1-fa8b6fabef9b.xml, ifsk.fsrtlinitializeextracreateparameter, ntifs/FsRtlInitializeExtraCreateParameter
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitializeExtraCreateParameter routine is available starting with Windows 7.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlInitializeExtraCreateParameter
 - ntifs/FsRtlInitializeExtraCreateParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlInitializeExtraCreateParameter
---

# FsRtlInitializeExtraCreateParameter function


## -description

The <b>FsRtlInitializeExtraCreateParameter</b> routine initializes an extra create parameter (ECP) context structure.

## -parameters

### -param Ecp [in]


Pointer to the ECP context structure to initialize.

### -param EcpFlags [in]


Defines initialization options. Currently, no flags are defined.

### -param CleanupCallback [in, optional]


Optional pointer to a filter-defined cleanup callback routine of type <a href="/previous-versions/ff551124(v=vs.85)">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>. The cleanup callback routine is called when the ECP context structure (created by the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlallocateextracreateparameter">FsRtlAllocateExtraCreateParameter</a> routine) is deleted. Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable.

### -param TotalSize [in]


The size, in bytes, of the ECP context structure to initialize.

### -param EcpType [in]


Pointer to a GUID that indicates the type of ECP for which the context structure will be initialized. For more information about ECPs, see <a href="/windows-hardware/drivers/ifs/using-extra-create-parameters-with-an-irp-mj-create-operation">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>.

### -param ListAllocatedFrom [in, optional]


Optional pointer to the list from which the ECP context structure is allocated.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlallocateextracreateparameter">FsRtlAllocateExtraCreateParameter</a>



<a href="/previous-versions/ff551124(v=vs.85)">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>
