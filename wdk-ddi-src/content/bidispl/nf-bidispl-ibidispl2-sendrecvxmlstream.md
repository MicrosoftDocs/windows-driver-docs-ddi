---
UID: NF:bidispl.IBidiSpl2.SendRecvXMLStream
title: IBidiSpl2::SendRecvXMLStream (bidispl.h)
description: The SendRecvXMLStream method sends a bidirectional printer communication request and receives the response as IStream objects formatted in accordance with the Bidirectional Communication Schemas.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl2::SendRecvXMLStream"]
ms.keywords: IBidiSpl2 interface [Print Devices],SendRecvXMLStream method, IBidiSpl2.SendRecvXMLStream, IBidiSpl2::SendRecvXMLStream, SendRecvXMLStream, SendRecvXMLStream method [Print Devices], SendRecvXMLStream method [Print Devices],IBidiSpl2 interface, _win32_IBidiSpl2_SendRecvXMLStream, bidispl/IBidiSpl2::SendRecvXMLStream, gdi.ibidispl2_ibidispl2__sendrecvxmlstream, print.ibidispl2_ibidispl2__sendrecvxmlstream
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
 - IBidiSpl2::SendRecvXMLStream
 - bidispl/IBidiSpl2::SendRecvXMLStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl2::SendRecvXMLStream
---

## -description

The **SendRecvXMLStream** method sends a bidirectional printer communication request and receives the response as [IStream](/windows/win32/api/objidl/nn-objidl-istream) objects formatted in accordance with the [Bidirectional Communication Schemas](/windows-hardware/drivers/print/bidirectional-communication-schema).

## -parameters

### -param pSRequest [in]

A pointer to the bidi communication request as a stream that complies with one of the [Bidirectional Communication Schemas](/windows-hardware/drivers/print/bidirectional-communication-schema).

### -param ppSResponse [out]

A pointer to the printer's response as a stream that complies with one of the [Bidirectional Communication Schemas](/windows-hardware/drivers/print/bidirectional-communication-schema).

## -returns

The method returns one of the following values.

| Return code | Description |
|---|---|
| **S_OK** | The operation was successful. |
| **E_HANDLE** | The interface handle is invalid. |
| **None of the above** | The **HRESULT** contains an error code that corresponds to the last error. |

Note that the **HRESULT** may contain a system error code that is defined in [Bidi Error Codes](/windows-hardware/drivers/print/bidi-error-codes).

## -remarks

The character encoding of *ppSResponse* is UTF-8. The character encoding of *pSRequest* is either UTF-8 or Unicode with a byte order mark OxFEFF.

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiSpl2](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl2)

[Print Spooler Components](/windows-hardware/drivers/print/print-spooler-components)
