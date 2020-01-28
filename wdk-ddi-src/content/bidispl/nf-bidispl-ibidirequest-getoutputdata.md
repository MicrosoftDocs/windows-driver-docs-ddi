---
UID: NF:bidispl.IBidiRequest.GetOutputData
title: IBidiRequest::GetOutputData (bidispl.h)
description: The GetOutputData method gets the specified output data coming back from the printer.
old-location: print\ibidirequest_ibidirequest__getoutputdata.htm
tech.root: print
ms.assetid: 0757dbc2-850b-4267-9339-b87591f85767
ms.date: 04/20/2018
ms.keywords: BIDI_BLOB, BIDI_BOOL, BIDI_ENUM, BIDI_FLOAT, BIDI_INT, BIDI_NULL, BIDI_STRING, BIDI_TEXT, GetOutputData, GetOutputData method [Print Devices], GetOutputData method [Print Devices],IBidiRequest interface, IBidiRequest interface [Print Devices],GetOutputData method, IBidiRequest.GetOutputData, IBidiRequest::GetOutputData, _win32_IBidiRequest_GetOutputData, bidispl/IBidiRequest::GetOutputData, gdi.ibidirequest_ibidirequest__getoutputdata, print.ibidirequest_ibidirequest__getoutputdata
f1_keywords:
 - "bidispl/IBidiRequest.GetOutputData"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- bidispl.dll
api_name:
- IBidiRequest.GetOutputData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequest::GetOutputData


## -description


The <b>GetOutputData</b> method gets the specified output data coming back from the printer.


## -parameters




### -param dwIndex [in]

A zero-based index of the output data that is requested. For more information, see Remarks.


### -param ppszSchema [out]

A pointer to a NULL-terminated string that receives the schema string. The caller must call the <a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree">CoTaskMemFree</a> function to free this pointer.


### -param pdwType [out]

A pointer to a variable that receives the type of the output data. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="BIDI_NULL"></a><a id="bidi_null"></a><dl>
<dt><b>BIDI_NULL</b></dt>
</dl>
</td>
<td width="60%">
No data.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_INT"></a><a id="bidi_int"></a><dl>
<dt><b>BIDI_INT</b></dt>
</dl>
</td>
<td width="60%">
Integer data.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_FLOAT"></a><a id="bidi_float"></a><dl>
<dt><b>BIDI_FLOAT</b></dt>
</dl>
</td>
<td width="60%">
Floating-point number.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_BOOL"></a><a id="bidi_bool"></a><dl>
<dt><b>BIDI_BOOL</b></dt>
</dl>
</td>
<td width="60%">
<b>TRUE</b> or <b>FALSE</b>.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_STRING"></a><a id="bidi_string"></a><dl>
<dt><b>BIDI_STRING</b></dt>
</dl>
</td>
<td width="60%">
Unicode character string.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_TEXT"></a><a id="bidi_text"></a><dl>
<dt><b>BIDI_TEXT</b></dt>
</dl>
</td>
<td width="60%">
Non-localizable Unicode string.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_ENUM"></a><a id="bidi_enum"></a><dl>
<dt><b>BIDI_ENUM</b></dt>
</dl>
</td>
<td width="60%">
Enumeration data in the form of a Unicode string.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_BLOB"></a><a id="bidi_blob"></a><dl>
<dt><b>BIDI_BLOB</b></dt>
</dl>
</td>
<td width="60%">
Binary data.

</td>
</tr>
</table>
 


### -param ppData [out]

A pointer to the variable that receives a pointer to the byte array containing the output data. The buffer is allocated by the COM interface to store the output data. The caller is responsible for calling <a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree">CoTaskMemFree</a> to free the buffer.


### -param uSize [out]

A pointer to a variable that receives the size of the byte array specified by **ppData.


## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Error Handling</a>.

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
The operation was successfully carried out.

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
At least one of the pointer variable parameters did not reference a valid memory location.

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



A single bidi request can have multiple results. The application calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getenumcount">GetEnumCount</a> to get the number of results from the bidi request.

If an application calls <b>GetOutputData</b> with the same index twice, the interface allocates two different buffers and thus the application must free both buffers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getenumcount">GetEnumCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest">IBidiRequest</a>
 

 

