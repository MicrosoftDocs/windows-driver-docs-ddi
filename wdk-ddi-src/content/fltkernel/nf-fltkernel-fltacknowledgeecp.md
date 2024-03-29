---
UID: NF:fltkernel.FltAcknowledgeEcp
title: FltAcknowledgeEcp function (fltkernel.h)
description: The FltAcknowledgeEcp routine is used to mark an extra create parameter context structure (ECP) as acknowledged.
old-location: ifsk\fltacknowledgeecp.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltAcknowledgeEcp function"]
ms.keywords: FltAcknowledgeEcp, FltAcknowledgeEcp routine [Installable File System Drivers], FltApiRef_a_to_d_17c8b1d4-47d1-4871-be9d-57986967a083.xml, fltkernel/FltAcknowledgeEcp, ifsk.fltacknowledgeecp
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
 - FltAcknowledgeEcp
 - fltkernel/FltAcknowledgeEcp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAcknowledgeEcp
---

# FltAcknowledgeEcp function


## -description

The <b>FltAcknowledgeEcp</b> routine is used to mark an extra create parameter context structure (ECP) as acknowledged.

## -parameters

### -param Filter [in]


Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpContext [in]


Pointer to the ECP to mark as acknowledged.

## -returns

None

## -remarks

This routine is available in Windows Vista and later. 

The ECP pointed to by the <i>EcpContext</i> parameter is marked as "acknowledged" by this routine.  This acknowledgment could indicate a number of things, including whether the ECP has been looked at, used, processed, and so on.  Note that the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpacknowledged">FltIsEcpAcknowledged</a> routine can be used to determine if a particular ECP has been marked as acknowledged.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpacknowledged">FltIsEcpAcknowledged</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpfromusermode">FltIsEcpFromUserMode</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>
