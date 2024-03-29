---
UID: NF:bidispl.IBidiSpl.SendRecv
title: IBidiSpl::SendRecv (bidispl.h)
description: The SendRecv method sends a bidi request to the printer.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl::SendRecv"]
ms.keywords: IBidiSpl interface [Print Devices],SendRecv method, IBidiSpl.SendRecv, IBidiSpl::SendRecv, SendRecv, SendRecv method [Print Devices], SendRecv method [Print Devices],IBidiSpl interface, _win32_IBidiSpl_SendRecv, bidispl/IBidiSpl::SendRecv, gdi.ibidispl_ibidispl__sendrecv, print.ibidispl_ibidispl__sendrecv
req.header: bidispl.h
req.include-header: 
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
req.dll: Bidispl.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IBidiSpl::SendRecv
 - bidispl/IBidiSpl::SendRecv
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl::SendRecv
---

## -description

The **SendRecv** method sends a bidi request to the printer.

## -parameters

### -param pszAction [in]

A pointer to a NULL-terminated string that specifies the action for this bidi request. It can be one of the following constants.

| Constant | Value | Description |
|---|---|---|
| BIDI_ACTION_ENUM_SCHEMA | L"EnumSchema" | Enumerate the schema. The returned data will be a list of schema that the port monitor or print provider supports. |
| BIDI_ACTION_GET | L"Get" | Get the value of a specified schema. |
| BIDI_ACTION_GET_ALL | L"GetAll" | Get the values of all child nodes of the specified schema. |
| BIDI_ACTION_SET | L"Set" | Set a value of the schema. |
| BIDI_ACTION_GET_WITH_ARGUMENT | L"GetWithArgument" | Request the bidi schema value using the data set as input argument. |

### -param pRequest [in]

A pointer to a single bidi request.

## -returns

The method returns one of the following values.

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

Note that the **HRESULT** may contain a system error code defined in [Bidi Error Codes](/windows-hardware/drivers/print/bidi-error-codes).

## -remarks

The BIDI_ACTION_* values are case insensitive strings.

## -see-also

[Bidirectional Communication Interfaces](../_print/index.md)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiSpl](./nn-bidispl-ibidispl.md)