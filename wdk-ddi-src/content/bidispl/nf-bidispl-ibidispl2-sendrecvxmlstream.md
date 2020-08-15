---
UID: NF:bidispl.IBidiSpl2.SendRecvXMLStream
title: IBidiSpl2::SendRecvXMLStream (bidispl.h)
description: The SendRecvXMLStream method sends a bidirectional printer communication request and receives the response as IStream objects formatted in accordance with the Bidirectional Communication Schemas.
old-location: print\ibidispl2_ibidispl2__sendrecvxmlstream.htm
tech.root: print
ms.assetid: 2daf99a8-42dc-4739-8e7e-80d3c9a084b7
ms.date: 04/20/2018
keywords: ["IBidiSpl2::SendRecvXMLStream"]
ms.keywords: IBidiSpl2 interface [Print Devices],SendRecvXMLStream method, IBidiSpl2.SendRecvXMLStream, IBidiSpl2::SendRecvXMLStream, SendRecvXMLStream, SendRecvXMLStream method [Print Devices], SendRecvXMLStream method [Print Devices],IBidiSpl2 interface, _win32_IBidiSpl2_SendRecvXMLStream, bidispl/IBidiSpl2::SendRecvXMLStream, gdi.ibidispl2_ibidispl2__sendrecvxmlstream, print.ibidispl2_ibidispl2__sendrecvxmlstream
f1_keywords:
 - "bidispl/IBidiSpl2.SendRecvXMLStream"
 - "IBidiSpl2.SendRecvXMLStream"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- bidispl.dll
api_name:
- IBidiSpl2.SendRecvXMLStream
targetos: Windows
req.typenames: 
---

# IBidiSpl2::SendRecvXMLStream


## -description


The <b>SendRecvXMLStream</b> method sends a bidirectional printer communication request and receives the response as <a href="https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream">IStream</a> objects formatted in accordance with the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schemas</a>.


## -parameters




### -param pSRequest 
[in]
A pointer to the bidi communication request as a stream that complies with one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schemas</a>.


### -param ppSResponse 
[out]
A pointer to the printer's response as a stream that complies with one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schemas</a>.


## -returns



The method returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code that corresponds to the last error.

</td>
</tr>
</table>
 

Note that the <b>HRESULT</b> may contain a system error code that is defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidi-error-codes">Bidi Error Codes</a>.




## -remarks



The character encoding of <i>ppSResponse</i> is UTF-8. The character encoding of <i>pSRequest</i> is either UTF-8 or Unicode with a byte order mark OxFEFF.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl2">IBidiSpl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/print-spooler-components">Print Spooler Components</a>
 

 

