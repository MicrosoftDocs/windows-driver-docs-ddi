---
UID: NF:ntifs.FsRtlIsEcpAcknowledged
title: FsRtlIsEcpAcknowledged function (ntifs.h)
description: The FsRtlIsEcpAcknowledged routine is used to determine if a given extra create parameter (ECP) context structure has been marked as acknowledged.
old-location: ifsk\fsrtlisecpacknowledged.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIsEcpAcknowledged function"]
ms.keywords: FsRtlIsEcpAcknowledged, FsRtlIsEcpAcknowledged routine [Installable File System Drivers], fsrtlref_5e05018f-5f4a-41e1-a05a-93ab636012e1.xml, ifsk.fsrtlisecpacknowledged, ntifs/FsRtlIsEcpAcknowledged
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlIsEcpAcknowledged routine is available starting with Windows Vista.
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
 - FsRtlIsEcpAcknowledged
 - ntifs/FsRtlIsEcpAcknowledged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIsEcpAcknowledged
---

# FsRtlIsEcpAcknowledged function


## -description

The <b>FsRtlIsEcpAcknowledged</b> routine is used to determine if a given extra create parameter (ECP) context structure has been marked as acknowledged.

## -parameters

### -param EcpContext [in]


Pointer to the ECP context structure to test for acknowledgment.

## -returns

The <b>FsRtlIsEcpAcknowledged </b>routine returns <b>TRUE</b> if the ECP was marked as acknowledged and <b>FALSE</b> otherwise.

## -remarks

To mark an ECP context structure as acknowledged, use the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacknowledgeecp">FltAcknowledgeEcp</a> routine.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacknowledgeecp">FltAcknowledgeEcp</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpfromusermode">FltIsEcpFromUserMode</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>
