---
UID: NC:mrx.PMRX_EXTRACT_NETROOT_NAME
title: PMRX_EXTRACT_NETROOT_NAME (mrx.h)
description: Learn more about the PMRX_EXTRACT_NETROOT_NAME callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_EXTRACT_NETROOT_NAME callback function"]
ms.keywords: MRxExtractNetRootName, MRxExtractNetRootName routine [Installable File System Drivers], PMRX_EXTRACT_NETROOT_NAME, ifsk.mrxextractnetrootname, mrx/MRxExtractNetRootName, mrxref_6ccbe7d3-a74d-4eab-bfc1-994791d9613a.xml
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
 - PMRX_EXTRACT_NETROOT_NAME
 - mrx/PMRX_EXTRACT_NETROOT_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_EXTRACT_NETROOT_NAME
---

# PMRX_EXTRACT_NETROOT_NAME callback function

## -description

The **MRxExtractNetRootName** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector extract the name of the NET_ROOT structure from a given pathname.

## -parameters

### -param FilePathName

[in] A pointer to a Unicode string that contains a pathname.

### -param SrvCall

[in] A pointer to the SRV_CALL structure.

### -param NetRootName

[out] On input, a pointer for storing a Unicode string. On success, this parameter will contain a pointer to a Unicode string that contains a NET_ROOT structure name.

### -param RestOfName

[out, optional] A pointer to a Unicode string that contains the rest of the name on success. This parameter is optional and can be a NULL pointer on input.

## -remarks

**MRxExtractNetRootName** parses the input name into the SRV_CALL structure, the NET_ROOT structure, and the rest of the pathname.

## -see-also

[**MRxCreateSrvCall**](nc-mrx-pmrx_create_srvcall.md)

[**MRxCreateVNetRoot**](nc-mrx-pmrx_create_v_net_root.md)

[**MRxFinalizeNetRoot**](nc-mrx-pmrx_finalize_net_root_calldown.md)

[**MRxFinalizeSrvCall**](nc-mrx-pmrx_finalize_srvcall_calldown.md)

[**MRxFinalizeVNetRoot**](nc-mrx-pmrx_finalize_v_net_root_calldown.md)

[**MRxPreparseName**](nc-mrx-pmrx_preparse_name.md)

[**MRxSrvCallWinnerNotify**](nc-mrx-pmrx_srvcall_winner_notify.md)
