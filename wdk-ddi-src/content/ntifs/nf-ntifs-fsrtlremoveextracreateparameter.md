---
UID: NF:ntifs.FsRtlRemoveExtraCreateParameter
title: FsRtlRemoveExtraCreateParameter function (ntifs.h)
description: The FsRtlRemoveExtraCreateParameter routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list.
old-location: ifsk\fsrtlremoveextracreateparameter.htm
tech.root: ifsk
ms.date: 09/10/2021
keywords: ["FsRtlRemoveExtraCreateParameter function"]
ms.keywords: FsRtlRemoveExtraCreateParameter, FsRtlRemoveExtraCreateParameter routine [Installable File System Drivers], fsrtlref_3fa961e9-0dc1-4d4b-a5dc-80883b1db15e.xml, ifsk.fsrtlremoveextracreateparameter, ntifs/FsRtlRemoveExtraCreateParameter
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: FsRtlRemoveExtraCreateParameter routine is available starting with Windows Vista.
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
 - FsRtlRemoveExtraCreateParameter
 - ntifs/FsRtlRemoveExtraCreateParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlRemoveExtraCreateParameter
---

# FsRtlRemoveExtraCreateParameter function

## -description

The **FsRtlRemoveExtraCreateParameter** routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list.

## -parameters

### -param EcpList [in, out]

Pointer to the extra create parameter (ECP) list that contains the ECP context structure to be detached from the given list.

### -param EcpType [in]

Pointer to a GUID that uniquely identifies the ECP context structure to be detached from the list.

### -param EcpContext [out]

Pointer to the detached ECP context structure.  If the ECP context structure is successfully detached from the given list, this parameter will be set to point to the detached ECP context structure.  If the ECP context structure is not found in the given ECP list, this parameter is set to **NULL**.

### -param EcpContextSize [out, optional]

Optional parameter that receives the size of the detached ECP context structure.  If this parameter is present when the routine is called, the parameter will receive the size, in bytes, of the detached ECP context structure.  If the given ECP context structure was not found in the given ECP list, this parameter is undefined.

## -returns

**FsRtlRemoveExtraCreateParameter** returns an NTSTATUS code such as one of the following:

| Return code      | Description |
| -----------      | ----------- |
| STATUS_SUCCESS   | The given ECP context structure was successfully detached from the given ECP list. |
| STATUS_NOT_FOUND | The given ECP context structure was not found in the given ECP list. |

## -remarks

The **FsRtlRemoveExtraCreateParameter** routine searches the ECP list given by the **EcpList** parameter for an ECP context structure given by the **EcpType** parameter.  If the ECP context structure exists in the list, **FsRtlRemoveExtraCreateParameter**  detaches the structure from the list, sets the **EcpContext** parameter to point to the structure, and returns STATUS_SUCCESS. If the ECP context structure does not exist in the list, **FsRtlRemoveExtraCreateParameter** sets the **EcpContext** parameter to **NULL** and returns STATUS_NOT_FOUND.

> [!NOTE]
> **FsRtlRemoveExtraCreateParameter** does not free the memory pool for the ECP context structure. To free the memory pool for the ECP context structure, first call **FsRtlRemoveExtraCreateParameter** to detach it from the list and then call the [**FltFreeExtraCreateParameter**](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md) routine to free the memory pool for the ECP context structure.

## -see-also

[**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[**FsRtlAllocateExtraCreateParameter**](nf-ntifs-fsrtlallocateextracreateparameter.md)

[**FsRtlAllocateExtraCreateParameterFromLookasideList**](nf-ntifs-fsrtlallocateextracreateparameterfromlookasidelist.md)

[**FltCreateFileEx2**](../fltkernel/nf-fltkernel-fltcreatefileex2.md)

[**FltFreeExtraCreateParameter**](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md)

[**FltGetEcpListFromCallbackData**](../fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata.md)

[**FltInsertExtraCreateParameter**](../fltkernel/nf-fltkernel-fltinsertextracreateparameter.md)

[**FltRemoveExtraCreateParameter**](../fltkernel/nf-fltkernel-fltremoveextracreateparameter.md)

[**FltSetEcpListIntoCallbackData**](../fltkernel/nf-fltkernel-fltsetecplistintocallbackdata.md)

[**IoCreateFileEx**](../ntddk/nf-ntddk-iocreatefileex.md)
