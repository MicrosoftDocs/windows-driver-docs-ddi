---
UID: NC:mrx.PMRX_COMPUTE_NEW_BUFFERING_STATE
title: PMRX_COMPUTE_NEW_BUFFERING_STATE (mrx.h)
description: Learn more about the PMRX_COMPUTE_NEW_BUFFERING_STATE callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_COMPUTE_NEW_BUFFERING_STATE callback function"]
ms.keywords: MRxComputeNewBufferingState, MRxComputeNewBufferingState routine [Installable File System Drivers], PMRX_COMPUTE_NEW_BUFFERING_STATE, ifsk.mrxcomputenewbufferingstate, mrx/MRxComputeNewBufferingState, mrxref_294ad2d0-2454-437d-818a-6879361f97e5.xml
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
 - PMRX_COMPUTE_NEW_BUFFERING_STATE
 - mrx/PMRX_COMPUTE_NEW_BUFFERING_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_COMPUTE_NEW_BUFFERING_STATE
---

# PMRX_COMPUTE_NEW_BUFFERING_STATE callback function

## -description

The**MRxComputeNewBufferingState** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that the network mini-redirector compute a new buffering state change.

## -parameters

### -param SrvOpen [in, out]

A pointer to the SRV_OPEN structure and the associated FCB structure.

### -param MRxContext [in]

A pointer to a context parameter for use by the network mini-redirector callback.

### -param NewBufferingState [out]

A pointer to where the new buffering state is stored when the routine returns.

## -returns

**MRxComputeNewBufferingState** returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_NOT_SUPPORTED | A feature that is requested is not supported. |

## -remarks

Before calling **MRxComputeNewBufferingState**, RDBSS sets the **FcbState** member of **SrvOpen****->Fcb** to FCB_STATE_BUFFERSTATE_CHANGING.

The Server Message Block (SMB) redirector uses **MRxComputeNewBufferingState** to map the SMB-specific oplock levels into the appropriate RDBSS buffering state flags. The oplock level is passed in the **MrxContext** parameter.

## -see-also

[**MRxCompleteBufferingStateChangeRequest**](nc-mrx-pmrx_change_buffering_state_calldown.md)

[**MRxGetConnectionId**](nc-mrx-pmrx_get_connection_id.md)
