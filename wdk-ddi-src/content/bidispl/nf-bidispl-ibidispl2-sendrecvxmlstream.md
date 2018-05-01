---
UID: NF:bidispl.IBidiSpl2.SendRecvXMLStream
title: IBidiSpl2::SendRecvXMLStream
author: windows-driver-content
description: The SendRecvXMLStream method sends a bidirectional printer communication request and receives the response as IStream objects formatted in accordance with the Bidirectional Communication Schemas.
old-location: print\ibidispl2_ibidispl2__sendrecvxmlstream.htm
old-project: print
ms.assetid: 2daf99a8-42dc-4739-8e7e-80d3c9a084b7
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IBidiSpl2 interface [Print Devices],SendRecvXMLStream method, IBidiSpl2.SendRecvXMLStream, IBidiSpl2::SendRecvXMLStream, SendRecvXMLStream, SendRecvXMLStream method [Print Devices], SendRecvXMLStream method [Print Devices],IBidiSpl2 interface, _win32_IBidiSpl2_SendRecvXMLStream, bidispl/IBidiSpl2::SendRecvXMLStream, gdi.ibidispl2_ibidispl2__sendrecvxmlstream, print.ibidispl2_ibidispl2__sendrecvxmlstream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	bidispl.dll
api_name:
-	IBidiSpl2.SendRecvXMLStream
product: Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl2::SendRecvXMLStream


## -description


The <b>SendRecvXMLStream</b> method sends a bidirectional printer communication request and receives the response as <a href="https://msdn.microsoft.com/c6f60e37-eadc-46a1-94f6-cacc23613531">IStream</a> objects formatted in accordance with the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.


## -parameters




### -param pSRequest [in]

A pointer to the bidi communication request as a stream that complies with one of the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.


### -param ppSResponse [out]

A pointer to the printer's response as a stream that complies with one of the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.


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
 

Note that the <b>HRESULT</b> may contain a system error code that is defined in <a href="https://msdn.microsoft.com/e273f5eb-e4f4-4aa7-9ed9-b418eebc6144">Bidi Error Codes</a>.




## -remarks



The character encoding of <i>ppSResponse</i> is UTF-8. The character encoding of <i>pSRequest</i> is either UTF-8 or Unicode with a byte order mark OxFEFF.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144981">IBidiSpl2</a>



<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>
 

 

