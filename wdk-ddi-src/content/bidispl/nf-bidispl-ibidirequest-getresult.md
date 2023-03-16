---
UID: NF:bidispl.IBidiRequest.GetResult
title: IBidiRequest::GetResult (bidispl.h)
description: The GetResult method tells whether the bidi request was successful.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiRequest::GetResult"]
ms.keywords: GetResult, GetResult method [Print Devices], GetResult method [Print Devices],IBidiRequest interface, IBidiRequest interface [Print Devices],GetResult method, IBidiRequest.GetResult, IBidiRequest::GetResult, _win32_IBidiRequest_GetResult, bidispl/IBidiRequest::GetResult, gdi.ibidirequest_ibidirequest__getresult, print.ibidirequest_ibidirequest__getresult
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
 - IBidiRequest::GetResult
 - bidispl/IBidiRequest::GetResult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequest::GetResult
---

## -description

The **GetResult** method tells whether the bidi request was successful.

## -parameters

### -param phr [out]

Pointer to a variable that specifies the status of the bidi request.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **E_POINTER** | At least one of the pointer variable parameters did not reference a valid memory location. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

The return value indicates whether the method was successful. It does not indicate what happened to the bidi request.

## -see-also

[Bidirectional Communication Interfaces](../_print/index.md)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiRequest](./nn-bidispl-ibidirequest.md)