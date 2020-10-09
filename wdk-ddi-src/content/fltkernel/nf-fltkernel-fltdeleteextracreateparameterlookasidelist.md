---
UID: NF:fltkernel.FltDeleteExtraCreateParameterLookasideList
title: FltDeleteExtraCreateParameterLookasideList function (fltkernel.h)
description: The FltDeleteExtraCreateParameterLookasideList routine frees an extra create parameter (ECP) lookaside list.
old-location: ifsk\fltdeleteextracreateparameterlookasidelist.htm
tech.root: ifsk
ms.assetid: 8df06f2c-7358-49ea-8948-b76c5090d75b
ms.date: 04/16/2018
keywords: ["FltDeleteExtraCreateParameterLookasideList function"]
ms.keywords: FltApiRef_a_to_d_ac849af2-706e-4eac-be0b-1c3c905ccdfe.xml, FltDeleteExtraCreateParameterLookasideList, FltDeleteExtraCreateParameterLookasideList routine [Installable File System Drivers], fltkernel/FltDeleteExtraCreateParameterLookasideList, ifsk.fltdeleteextracreateparameterlookasidelist
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDeleteExtraCreateParameterLookasideList
 - fltkernel/FltDeleteExtraCreateParameterLookasideList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDeleteExtraCreateParameterLookasideList
---

# FltDeleteExtraCreateParameterLookasideList function


## -description

The <b>FltDeleteExtraCreateParameterLookasideList </b>routine frees an extra create parameter (ECP) lookaside list.

## -parameters

### -param Filter 

[in]
Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param Lookaside 

[in, out]
Pointer to an opaque <a href="/windows-hardware/drivers/kernel/eprocess">PAGED_LOOKASIDE_LIST</a> or <a href="/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a> lookaside  list-head structure that represents the lookaside list to be freed.

### -param Flags 

[in]
Communicates ECP lookaside list allocation options that were used when the lookaside list was initialized by the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitextracreateparameterlookasidelist">FltInitExtraCreateParameterLookasideList</a> routine. 

This <i>Flags</i> parameter should be the same as the <i>Flags</i> parameter used in the call to the <b>FltInitExtraCreateParameterLookasideList</b> routine.

## -returns

None

## -remarks

This routine is available starting with Windows Vista. 

The <b>FltDeleteExtraCreateParameterLookasideList </b>routine frees the given ECP lookaside list. However, freeing the lookaside list does not automatically free any ECP context structures allocated from the lookaside list.  To free an ECP context structure allocated from a lookaside list, call the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a> routine.

Drivers must explicitly free all ECP context structures and ECP lookaside lists that they created before unloading.  For more information, see <a href="/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>



<a href="/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a>



<a href="/windows-hardware/drivers/kernel/eprocess">PAGED_LOOKASIDE_LIST</a>



<a href="/previous-versions/ff551124(v=vs.85)">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>