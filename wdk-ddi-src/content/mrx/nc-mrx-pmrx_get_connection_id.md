---
UID: NC:mrx.PMRX_GET_CONNECTION_ID
title: PMRX_GET_CONNECTION_ID (mrx.h)
description: Learn more about PMRX_GET_CONNECTION_ID callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_GET_CONNECTION_ID callback function"]
ms.keywords: MRxGetConnectionId, MRxGetConnectionId routine [Installable File System Drivers], PMRX_GET_CONNECTION_ID, ifsk.mrxgetconnectionid, mrx/MRxGetConnectionId, mrxref_14943242-5da1-4404-bc5b-b86c2a88b347.xml
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
 - PMRX_GET_CONNECTION_ID
 - mrx/PMRX_GET_CONNECTION_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_GET_CONNECTION_ID
---

# PMRX_GET_CONNECTION_ID callback function

## -description

The**MRxGetConnectionId** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions.

## -parameters

### -param RxContext

[in, out] A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

### -param UniqueId

[in, out] A pointer to the connection ID when the routine returns.

## -returns

**MRxGetConnectionId** returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_NOT_IMPLEMENTED | This routine is not implemented.

## -remarks

**MRxGetConnectionId** is called by RDBSS when trying to find or construct a V_NET_ROOT structure.

If connection IDs are supported by the network mini-redirector, then the returned connection ID is appended to the NET_ROOT structure name stored in the NetName table used by RDBSS for storing network names. RDBSS considers the connection ID as an opaque blob, and does a byte-by-byte comparison of the connection ID blob while looking up the NetName table for a given name with a connection ID.

## -see-also

[**MRxCompleteBufferingStateChangeRequest**](nc-mrx-pmrx_change_buffering_state_calldown.md)

[**MRxComputeNewBufferingState**](nc-mrx-pmrx_compute_new_buffering_state.md)
