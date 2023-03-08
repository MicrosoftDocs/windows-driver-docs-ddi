---
UID: NF:bidispl.IBidiSpl2.SendRecvXMLString
title: IBidiSpl2::SendRecvXMLString (bidispl.h)
description: The SendRecvXMLString method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the Bidirectional Communication Schemas.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl2::SendRecvXMLString"]
ms.keywords: IBidiSpl2 interface [Print Devices],SendRecvXMLString method, IBidiSpl2.SendRecvXMLString, IBidiSpl2::SendRecvXMLString, SendRecvXMLString, SendRecvXMLString method [Print Devices], SendRecvXMLString method [Print Devices],IBidiSpl2 interface, _win32_IBidiSpl2_SendRecvXMLString, bidispl/IBidiSpl2::SendRecvXMLString, gdi.ibidispl2_ibidispl2__sendrecvxmlstring, print.ibidispl2_ibidispl2__sendrecvxmlstring
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
 - IBidiSpl2::SendRecvXMLString
 - bidispl/IBidiSpl2::SendRecvXMLString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl2::SendRecvXMLString
---

## -description

The **SendRecvXMLString** method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the [Bidirectional Communication Schemas](/windows-hardware/drivers/print/bidirectional-communication-schema).

## -parameters

### -param bstrRequest [in]

The bidi communication request as a Unicode string that complies with one of the [Bidirectional Communication Schemas](/windows-hardware/drivers/print/bidirectional-communication-schema).

### -param pbstrResponse [out]

A pointer to the printer's response as a Unicode string that complies with one of the [Bidirectional Communication Schemas](/windows-hardware/drivers/print/bidirectional-communication-schema).

## -returns

The method returns one of the following values.

| Value | Description |
|---|---|
| **S_OK** | The operation was successful. |
| **E_HANDLE** | The interface handle is invalid. |
| **None of the above** | The **HRESULT** contains an error code that corresponds to the last error. |

The **HRESULT** may contain a system error code that is defined in [Bidi Error Codes](/windows-hardware/drivers/print/bidi-error-codes).

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[IBidiSpl2](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl2)

[Print Spooler Components](/windows-hardware/drivers/print/print-spooler-components)
