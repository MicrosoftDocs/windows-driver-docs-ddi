---
UID: NF:bidispl.IBidiRequest.GetEnumCount
title: IBidiRequest::GetEnumCount (bidispl.h)
description: The GetEnumCount method gets the number of output results from the bidi request.
old-location: print\ibidirequest_ibidirequest__getenumcount.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IBidiRequest::GetEnumCount"]
ms.keywords: GetEnumCount, GetEnumCount method [Print Devices], GetEnumCount method [Print Devices],IBidiRequest interface, IBidiRequest interface [Print Devices],GetEnumCount method, IBidiRequest.GetEnumCount, IBidiRequest::GetEnumCount, _win32_IBidiRequest_GetEnumCount, bidispl/IBidiRequest::GetEnumCount, gdi.ibidirequest_ibidirequest__getenumcount, print.ibidirequest_ibidirequest__getenumcount
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
 - IBidiRequest::GetEnumCount
 - bidispl/IBidiRequest::GetEnumCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequest.GetEnumCount
---

# IBidiRequest::GetEnumCount


## -description

The <b>GetEnumCount</b> method gets the number of output results from the bidi request.

## -parameters

### -param pdwTotal 

[out]
A pointer to a variable that receives the number of output results.

## -returns

The method returns one of the following values. For more information about COM error codes, see <a href="/windows-hardware/drivers/ddi/index">Error Handling</a>.

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

A single bidi request can have multiple results. After calling <b>GetEnumCount</b>, the application can call <a href="/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getoutputdata">GetOutputData</a> to select a particular result.

## -see-also

<a href="/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getoutputdata">GetOutputData</a>



<a href="/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest">IBidiRequest</a>
