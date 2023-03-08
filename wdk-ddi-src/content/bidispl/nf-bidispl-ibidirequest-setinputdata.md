---
UID: NF:bidispl.IBidiRequest.SetInputData
title: IBidiRequest::SetInputData (bidispl.h)
description: The SetInputData method sets the data to send to the printer.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiRequest::SetInputData"]
ms.keywords: BIDI_BLOB, BIDI_BOOL, BIDI_ENUM, BIDI_FLOAT, BIDI_INT, BIDI_NULL, BIDI_STRING, BIDI_TEXT, IBidiRequest interface [Print Devices],SetInputData method, IBidiRequest.SetInputData, IBidiRequest::SetInputData, SetInputData, SetInputData method [Print Devices], SetInputData method [Print Devices],IBidiRequest interface, _win32_IBidiRequest_SetInputData, bidispl/IBidiRequest::SetInputData, gdi.ibidirequest_ibidirequest__setinputdata, print.ibidirequest_ibidirequest__setinputdata
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
 - IBidiRequest::SetInputData
 - bidispl/IBidiRequest::SetInputData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequest::SetInputData
---

## -description

The **SetInputData** method sets the data to send to the printer.

## -parameters

### -param dwType [in]

The type of data to be sent. This parameter can be one of the following values.

| Value | Description |
|---|---|
| **BIDI_NULL** | No data. |
| **BIDI_INT** | Integer data. |
| **BIDI_FLOAT** | Floating-point number. |
| **BIDI_BOOL** | **TRUE** or **FALSE** |
| **BIDI_STRING** | Unicode character string. |
| **BIDI_TEXT** | Non-localizable Unicode string. |
| **BIDI_ENUM** | Enumeration data in the form of a Unicode string. |
| **BIDI_BLOB** | Binary data. |

### -param pData [in]

A pointer to the byte array that contains the data. For example, if *dwType* is BIDI_BOOL, *pData* points to a buffer that contains a Boolean value and if *dwType* is BIDI_BLOB, *pData* points to a buffer that contains the binary data.

### -param uSize [in]

Size, in bytes, of the byte array specified by *pData*.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **E_INVALIDARG** | The type of the data was not consistent with its size. |
| **E_OUTOFMEMORY** | Memory allocation failed. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -remarks

If an application calls **SetInputData** more than once, only the value of the last call will be set.

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiRequest](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest)
