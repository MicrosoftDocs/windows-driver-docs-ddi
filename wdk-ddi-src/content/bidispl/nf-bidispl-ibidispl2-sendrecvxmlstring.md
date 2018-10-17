---
UID: NF:bidispl.IBidiSpl2.SendRecvXMLString
title: IBidiSpl2::SendRecvXMLString
author: windows-driver-content
description: The SendRecvXMLString method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the Bidirectional Communication Schemas.
old-location: print\ibidispl2_ibidispl2__sendrecvxmlstring.htm
tech.root: print
ms.assetid: 7d61402e-e248-4770-a828-9c266e528115
ms.date: 4/20/2018
ms.keywords: IBidiSpl2 interface [Print Devices],SendRecvXMLString method, IBidiSpl2.SendRecvXMLString, IBidiSpl2::SendRecvXMLString, SendRecvXMLString, SendRecvXMLString method [Print Devices], SendRecvXMLString method [Print Devices],IBidiSpl2 interface, _win32_IBidiSpl2_SendRecvXMLString, bidispl/IBidiSpl2::SendRecvXMLString, gdi.ibidispl2_ibidispl2__sendrecvxmlstring, print.ibidispl2_ibidispl2__sendrecvxmlstring
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
-	IBidiSpl2.SendRecvXMLString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl2::SendRecvXMLString


## -description


The <b>SendRecvXMLString</b> method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.


## -parameters




### -param bstrRequest [in]

The bidi communication request as a Unicode string that complies with one of the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.


### -param pbstrResponse [out]

A pointer to the printer's response as a Unicode string that complies with one of the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.


## -returns



The method returns one of the following values.

<table>
<tr>
<th>Value</th>
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




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144981">IBidiSpl2</a>



<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>
 

 

