---
UID: NF:bidispl.IBidiRequest.GetOutputData
title: IBidiRequest::GetOutputData (bidispl.h)
description: The GetOutputData method gets the specified output data coming back from the printer.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiRequest::GetOutputData"]
ms.keywords: BIDI_BLOB, BIDI_BOOL, BIDI_ENUM, BIDI_FLOAT, BIDI_INT, BIDI_NULL, BIDI_STRING, BIDI_TEXT, GetOutputData, GetOutputData method [Print Devices], GetOutputData method [Print Devices],IBidiRequest interface, IBidiRequest interface [Print Devices],GetOutputData method, IBidiRequest.GetOutputData, IBidiRequest::GetOutputData, _win32_IBidiRequest_GetOutputData, bidispl/IBidiRequest::GetOutputData, gdi.ibidirequest_ibidirequest__getoutputdata, print.ibidirequest_ibidirequest__getoutputdata
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
 - IBidiRequest::GetOutputData
 - bidispl/IBidiRequest::GetOutputData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequest::GetOutputData
---

## -description

The **GetOutputData** method gets the specified output data coming back from the printer.

## -parameters

### -param dwIndex [in]

A zero-based index of the output data that is requested. For more information, see Remarks.

### -param ppszSchema [out]

A pointer to a NULL-terminated string that receives the schema string. The caller must call the [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) function to free this pointer.

### -param pdwType [out]

A pointer to a variable that receives the type of the output data. This parameter can be one of the following values.

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

### -param ppData [out]

A pointer to the variable that receives a pointer to the byte array containing the output data. The buffer is allocated by the COM interface to store the output data. The caller is responsible for calling [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) to free the buffer.

### -param uSize [out]

A pointer to a variable that receives the size of the byte array specified by **ppData.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Return code | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **E_POINTER** | At least one of the pointer variable parameters did not reference a valid memory location. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -remarks

A single bidi request can have multiple results. The application calls [GetEnumCount](/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getenumcount) to get the number of results from the bidi request.

If an application calls **GetOutputData** with the same index twice, the interface allocates two different buffers and thus the application must free both buffers.

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[GetEnumCount](/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getenumcount)

[IBidiRequest](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest)
