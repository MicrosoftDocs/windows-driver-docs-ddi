---
UID: NF:bidispl.IBidiRequest.GetEnumCount
title: IBidiRequest::GetEnumCount (bidispl.h)
description: The GetEnumCount method gets the number of output results from the bidi request.
old-location: print\ibidirequest_ibidirequest__getenumcount.htm
tech.root: print
ms.assetid: 4c857ff4-02c1-487b-bdb0-44d62a4cf4a1
ms.date: 04/20/2018
ms.keywords: GetEnumCount, GetEnumCount method [Print Devices], GetEnumCount method [Print Devices],IBidiRequest interface, IBidiRequest interface [Print Devices],GetEnumCount method, IBidiRequest.GetEnumCount, IBidiRequest::GetEnumCount, _win32_IBidiRequest_GetEnumCount, bidispl/IBidiRequest::GetEnumCount, gdi.ibidirequest_ibidirequest__getenumcount, print.ibidirequest_ibidirequest__getenumcount
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	bidispl.dll
api_name:
-	IBidiRequest.GetEnumCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequest::GetEnumCount


## -description


The <b>GetEnumCount</b> method gets the number of output results from the bidi request.


## -parameters




### -param pdwTotal [out]

A pointer to a variable that receives the number of output results.


## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.

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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
The <i>pdwTotal</i> parameter did not point to a valid memory location.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code corresponding to the last error.

</td>
</tr>
</table>
 




## -remarks



A single bidi request can have multiple results. After calling <b>GetEnumCount</b>, the application can call <a href="https://msdn.microsoft.com/0757dbc2-850b-4267-9339-b87591f85767">GetOutputData</a> to select a particular result.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="https://msdn.microsoft.com/0757dbc2-850b-4267-9339-b87591f85767">GetOutputData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144969">IBidiRequest</a>
 

 

