---
UID: NF:bidispl.IBidiRequest.SetSchema
title: IBidiRequest::SetSchema (bidispl.h)
description: The SetSchema method sets the bidi schema string.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiRequest::SetSchema"]
ms.keywords: IBidiRequest interface [Print Devices],SetSchema method, IBidiRequest.SetSchema, IBidiRequest::SetSchema, SetSchema, SetSchema method [Print Devices], SetSchema method [Print Devices],IBidiRequest interface, _win32_IBidiRequest_SetSchema, bidispl/IBidiRequest::SetSchema, gdi.ibidirequest_ibidirequest__setschema, print.ibidirequest_ibidirequest__setschema
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
req.dll: Bidispl.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IBidiRequest::SetSchema
 - bidispl/IBidiRequest::SetSchema
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequest::SetSchema
---

## -description

The **SetSchema** method sets the bidi schema string.

## -parameters

### -param pszSchema [in]

Pointer to a schema string.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiRequest](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest)
