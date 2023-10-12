---
UID: NC:mrx.PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
title: PMRX_CHANGE_BUFFERING_STATE_CALLDOWN (mrx.h)
description: Learn more about the PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback function"]
ms.keywords: MRxCompleteBufferingStateChangeRequest, MRxCompleteBufferingStateChangeRequest routine [Installable File System Drivers], PMRX_CHANGE_BUFFERING_STATE_CALLDOWN, ifsk.mrxcompletebufferingstatechangerequest, mrx/MRxCompleteBufferingStateChangeRequest, mrxref_5ac31893-1998-454a-a0c9-07d32e60d8db.xml
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
 - PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
 - mrx/PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
---

# PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback function

## -description

The**MRxCompleteBufferingStateChangeRequest** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to notify the network mini-redirector that a buffering state change request has been completed.

## -parameters

### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

### -param SrvOpen [in, out]

A pointer to a context parameter for use by the network mini-redirector callback routine.

### -param MRxContext [in]

A pointer to the SRV_OPEN structure and the associated FCB structure to be changed.

## -returns

**MRxCompleteBufferingStateChangeRequest** returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_NOT_SUPPORTED | An option in the  buffering request change is not supported. |

## -remarks

Before calling **MRxCompleteBufferingStateChangeRequest**, RDBSS:

* Acquires an exclusive lock on the FCB structure.

* Sets the **FcbState** member of **SrvOpen->Fcb** to FCB_STATE_BUFFERSTATE_CHANGING.

* Modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

  * **pRelevantSrvOpen** is set to the SRV_OPEN structure.
  * **pFcb** is set to the FCB structure.
  * **pFobx** is set to the FOBX structure.

If lock buffering is enabled, **MRxCompleteBufferingStateChangeRequest** will need to flush out the byte-range locks to the server. The list of locked regions is passed to the network mini-redirector in the **LowIoContext.ParamsFor.Locks.LockList** member of the RX_CONTEXT structure.

The Server Message Block (SMB) redirector uses **MRxCompleteBufferingStateChangeRequest** to send an oplock break response or to close the handle on an oplock break if the file is no longer in use. Byte range locks that need to be flushed out to the server are passed to the network mini-redirector in the **LowIoContext.ParamsFor.Locks.LockList** member of the RX_CONTEXT structure. The new oplock level is passed in the **MrxContext** parameter.

RDBSS ignores the return value from **MRxCompleteBufferingStateChangeRequest**.

## -see-also

[**MRxComputeNewBufferingState**](nc-mrx-pmrx_compute_new_buffering_state.md)

[**MRxGetConnectionId**](nc-mrx-pmrx_get_connection_id.md)
