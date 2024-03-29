---
UID: NF:fltkernel.FltIsEcpFromUserMode
title: FltIsEcpFromUserMode function (fltkernel.h)
description: The FltIsEcpFromUserMode routine is used to determine if an extra create parameter context structure (ECP) originated from user mode.
old-location: ifsk\fltisecpfromusermode.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltIsEcpFromUserMode function"]
ms.keywords: FltApiRef_e_to_o_ea63cca7-3efb-4b45-b075-7efbc8138f88.xml, FltIsEcpFromUserMode, FltIsEcpFromUserMode routine [Installable File System Drivers], fltkernel/FltIsEcpFromUserMode, ifsk.fltisecpfromusermode
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
 - FltIsEcpFromUserMode
 - fltkernel/FltIsEcpFromUserMode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - FltMgr.sys
api_name:
 - FltIsEcpFromUserMode
---

# FltIsEcpFromUserMode function


## -description

The <b>FltIsEcpFromUserMode </b>routine is used to determine if an extra create parameter context structure (ECP) originated from user mode.

## -parameters

### -param Filter [in]


Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpContext [in]


Pointer to the ECP to test.

## -returns

The routine returns <b>TRUE</b> if the ECP originated in user mode and <b>FALSE</b> if the ECP originated in kernel mode.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacknowledgeecp">FltAcknowledgeEcp</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>
