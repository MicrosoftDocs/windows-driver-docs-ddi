---
UID: NF:bidispl.IBidiSpl.MultiSendRecv
title: IBidiSpl::MultiSendRecv (bidispl.h)
description: The MultiSendRecv method sends a list of bidi requests.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl::MultiSendRecv"]
ms.keywords: IBidiSpl interface [Print Devices],MultiSendRecv method, IBidiSpl.MultiSendRecv, IBidiSpl::MultiSendRecv, MultiSendRecv, MultiSendRecv method [Print Devices], MultiSendRecv method [Print Devices],IBidiSpl interface, _win32_IBidiSpl_MultiSendRecv, bidispl/IBidiSpl::MultiSendRecv, gdi.ibidispl_ibidispl__multisendrecv, print.ibidispl_ibidispl__multisendrecv
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
 - IBidiSpl::MultiSendRecv
 - bidispl/IBidiSpl::MultiSendRecv
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl::MultiSendRecv
---

## -description

The **MultiSendRecv** method sends a list of bidi requests.

## -parameters

### -param pszAction [in]

A pointer to a NULL-terminated string that specifies the action for this bidi request. It can be one of the following constants.

| Constant | Value | Description |
|---|---|---|
| BIDI_ACTION_ENUM_SCHEMA | L"EnumSchema" | Enumerate the schema. The returned data will be a list of schema that the port monitor or print provider supports. |
| BIDI_ACTION_GET | L"Get" | Get the value of a specified schema. |
| BIDI_ACTION_GET_ALL | L"GetAll" | Get the values of all child nodes of the specified schema. |
| BIDI_ACTION_SET | L"Set" | Set a value of the schema. |

### -param pRequestContainer [in]

A pointer to the list of bidi requests.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

The **HRESULT** may contain a system error code defined in [Bidi Error Codes](/windows-hardware/drivers/print/bidi-error-codes).

## -remarks

The BIDI_ACTION_* values are case insensitive strings.

## -see-also

[Bidirectional Communication Interfaces](../_print/index.md)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiSpl](./nn-bidispl-ibidispl.md)