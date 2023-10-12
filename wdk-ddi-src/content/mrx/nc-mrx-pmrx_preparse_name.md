---
UID: NC:mrx.PMRX_PREPARSE_NAME
title: PMRX_PREPARSE_NAME (mrx.h)
description: Learn more about the PMRX_PREPARSE_NAME callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_PREPARSE_NAME callback function"]
ms.keywords: MRxPreparseName, MRxPreparseName routine [Installable File System Drivers], PMRX_PREPARSE_NAME, ifsk.mrxpreparsename, mrx/MRxPreparseName, mrxref_4f7f0d54-93a0-4b61-bf62-6e7b1063415c.xml
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_PREPARSE_NAME
 - mrx/PMRX_PREPARSE_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_PREPARSE_NAME
---

# PMRX_PREPARSE_NAME callback function

## -description

The **MRxPreparseName** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to give a network mini-redirector the opportunity to preparse a name.

## -parameters

### -param RxContext

[in, out] A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

### -param Name

[in] A pointer to a Unicode string that contains the name string.

## -returns

**MRxPreparseName** returns STATUS_SUCCESS on success.

## -remarks

**MRxPreparseName** is called by RDBSS after parsing a name to give a network mini-redirector a final opportunity to preparse the name.

RDBSS tries to convert the name to its canonical form, removing a dot (".") and two dots (".."), before calling **MRxPreparseName**. RDBSS will also parse the format used by NTFS streams.

RDBSS ignores the return value from **MRxPreparseName**.

## -see-also

[**MRxCreateSrvCall**](nc-mrx-pmrx_create_srvcall.md)

[**MRxCreateVNetRoot**](nc-mrx-pmrx_create_v_net_root.md)

[**MRxExtractNetRootName**](nc-mrx-pmrx_extract_netroot_name.md)

[**MRxFinalizeNetRoot**](nc-mrx-pmrx_finalize_net_root_calldown.md)

[**MRxFinalizeVNetRoot**](nc-mrx-pmrx_finalize_v_net_root_calldown.md)

[**MRxSrvCallWinnerNotify**](nc-mrx-pmrx_srvcall_winner_notify.md)

[**RxFinalizeSrvCall**](../fcb/nf-fcb-rxfinalizesrvcall.md)
