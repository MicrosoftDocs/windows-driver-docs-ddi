---
UID: NF:bidispl.IBidiRequest.GetEnumCount
title: IBidiRequest::GetEnumCount (bidispl.h)
description: The GetEnumCount method gets the number of output results from the bidi request.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiRequest::GetEnumCount"]
ms.keywords: GetEnumCount, GetEnumCount method [Print Devices], GetEnumCount method [Print Devices],IBidiRequest interface, IBidiRequest interface [Print Devices],GetEnumCount method, IBidiRequest.GetEnumCount, IBidiRequest::GetEnumCount, _win32_IBidiRequest_GetEnumCount, bidispl/IBidiRequest::GetEnumCount, gdi.ibidirequest_ibidirequest__getenumcount, print.ibidirequest_ibidirequest__getenumcount
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
 - IBidiRequest::GetEnumCount
 - bidispl/IBidiRequest::GetEnumCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequest::GetEnumCount
---

## -description

The **GetEnumCount** method gets the number of output results from the bidi request.

## -parameters

### -param pdwTotal [out]

A pointer to a variable that receives the number of output results.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The method was successful. |
| **E_HANDLE** | The interface handle was invalid. |
| **E_POINTER** | The *pdwTotal* parameter did not point to a valid memory location. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -remarks

A single bidi request can have multiple results. After calling **GetEnumCount**, the application can call [GetOutputData](./nf-bidispl-ibidirequest-getoutputdata.md) to select a particular result.

## -see-also

[Bidirectional Communication Interfaces](../_print/index.md)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[GetOutputData](./nf-bidispl-ibidirequest-getoutputdata.md)

[IBidiRequest](./nn-bidispl-ibidirequest.md)