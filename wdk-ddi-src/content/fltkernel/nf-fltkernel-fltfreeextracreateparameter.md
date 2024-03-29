---
UID: NF:fltkernel.FltFreeExtraCreateParameter
title: FltFreeExtraCreateParameter function (fltkernel.h)
description: The FltFreeExtraCreateParameter routine frees the memory for an ECP context structure.
old-location: ifsk\fltfreeextracreateparameter.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltFreeExtraCreateParameter function"]
ms.keywords: FltApiRef_e_to_o_d5948c86-8750-4684-9f66-0f0b34949714.xml, FltFreeExtraCreateParameter, FltFreeExtraCreateParameter routine [Installable File System Drivers], fltkernel/FltFreeExtraCreateParameter, ifsk.fltfreeextracreateparameter
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.lib: FltMgr.lib
req.dll: FltMgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFreeExtraCreateParameter
 - fltkernel/FltFreeExtraCreateParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - FltMgr.sys
api_name:
 - FltFreeExtraCreateParameter
---

# FltFreeExtraCreateParameter function


## -description

The <b>FltFreeExtraCreateParameter</b> routine frees the memory for an ECP context structure.

## -parameters

### -param Filter [in]


Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpContext [in]


Pointer to the extra create parameter (ECP) context structure to be freed.

## -returns

None.

## -remarks

If the ECP context structure to be freed is still attached to an ECP list, it must first be detached from the list by the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a> routine before the <b>FltFreeExtraCreateParameter</b> routine can be called to free it.

If a cleanup callback routine of type PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK was defined for the given ECP context structure, this callback routine is invoked upon deletion of the ECP context structure.  For more information, see <a href="/previous-versions/ff551124(v=vs.85)">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>



<a href="/previous-versions/ff551124(v=vs.85)">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>
