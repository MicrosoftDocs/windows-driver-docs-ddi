---
UID: NF:bidispl.IBidiRequest.GetOutputData
title: IBidiRequest::GetOutputData method
author: windows-driver-content
description: The GetOutputData method gets the specified output data coming back from the printer.
old-location: print\ibidirequest_ibidirequest__getoutputdata.htm
old-project: print
ms.assetid: 0757dbc2-850b-4267-9339-b87591f85767
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, B, BIDI_BLOB, BIDI_BOOL, BIDI_ENUM, BIDI_FLOAT, BIDI_INT, BIDI_NULL, BIDI_STRING, BIDI_TEXT, D, G, GetOutputData method [Print Devices], GetOutputData method [Print Devices], IBidiRequest interface, GetOutputData,IBidiRequest.GetOutputData, I, IBidiRequest, IBidiRequest interface [Print Devices], GetOutputData method, IBidiRequest::GetOutputData, O, R, _win32_IBidiRequest_GetOutputData, a, bidispl/IBidiRequest::GetOutputData, d, e, gdi.ibidirequest_ibidirequest__getoutputdata, i, p, print.ibidirequest_ibidirequest__getoutputdata, q, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: bidispl.h
req.dll: Bidispl.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	bidispl.dll
apiname:
-	IBidiRequest.GetOutputData
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# IBidiRequest::GetOutputData method


## -description


The <b>GetOutputData</b> method gets the specified output data coming back from the printer.


## -syntax


````
HRESULT GetOutputData(
  [in]  const DWORD  dwIndex,
  [out]       LPWSTR *ppszSchema,
  [out]       DWORD  *pdwType,
  [out]       BYTE   **ppData,
  [out]       ULONG  *uSize
);
````


## -parameters




### -param dwIndex [in]

A zero-based index of the output data that is requested. For more information, see Remarks.


### -param ppszSchema [out]

A pointer to a NULL-terminated string that receives the schema string. The caller must call the <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms680722">CoTaskMemFree</a> function to free this pointer.


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

A pointer to the variable that receives a pointer to the byte array containing the output data. The buffer is allocated by the COM interface to store the output data. The caller is responsible for calling <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms680722">CoTaskMemFree</a> to free the buffer.


### -param uSize [out]

A pointer to a variable that receives the size of the byte array specified by **ppData.


## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.

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



A single bidi request can have multiple results. The application calls <a href="https://msdn.microsoft.com/4c857ff4-02c1-487b-bdb0-44d62a4cf4a1">GetEnumCount</a> to get the number of results from the bidi request.

If an application calls <b>GetOutputData</b> with the same index twice, the interface allocates two different buffers and thus the application must free both buffers.




## -see-also

<a href="https://msdn.microsoft.com/4c857ff4-02c1-487b-bdb0-44d62a4cf4a1">GetEnumCount</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="..\bidispl\nn-bidispl-ibidirequest.md">IBidiRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest::GetOutputData method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

