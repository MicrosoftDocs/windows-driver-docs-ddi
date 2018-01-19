---
UID: NF:bidispl.IBidiRequest.GetOutputData
title: IBidiRequest::GetOutputData method
author: windows-driver-content
description: The IBidiRequest::GetOutputData method gets the specified output data coming back from the printer.
old-location: print\ibidirequest_ibidirequest__getoutputdata.htm
old-project: print
ms.assetid: 0757dbc2-850b-4267-9339-b87591f85767
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IBidiRequest, IBidiRequest::GetOutputData, GetOutputData
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
req.alt-api: IBidiRequest.IBidiRequest::GetOutputData
req.alt-loc: bidispl.dll
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
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# IBidiRequest::GetOutputData method



## -description
The <b>IBidiRequest::GetOutputData</b> method gets the specified output data coming back from the printer.



## -syntax

````
HRESULT IBidiRequest::GetOutputData(
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

A pointer to a NULL-terminated string that receives the schema string. The caller must call the <a href="_com_cotaskmemfree">CoTaskMemFree</a> function to free this pointer.


### -param pdwType [out]

A pointer to a variable that receives the type of the output data. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param BIDI_NULL

</td>
<td width="60%">
No data.

</td>
</tr>
<tr>

### -param BIDI_INT

</td>
<td width="60%">
Integer data.

</td>
</tr>
<tr>

### -param BIDI_FLOAT

</td>
<td width="60%">
Floating-point number.

</td>
</tr>
<tr>

### -param BIDI_BOOL

</td>
<td width="60%">
<b>TRUE</b> or <b>FALSE</b>.

</td>
</tr>
<tr>

### -param BIDI_STRING

</td>
<td width="60%">
Unicode character string.

</td>
</tr>
<tr>

### -param BIDI_TEXT

</td>
<td width="60%">
Non-localizable Unicode string.

</td>
</tr>
<tr>

### -param BIDI_ENUM

</td>
<td width="60%">
Enumeration data in the form of a Unicode string.

</td>
</tr>
<tr>

### -param BIDI_BLOB

</td>
<td width="60%">
Binary data.

</td>
</tr>
</table>
 


### -param ppData [out]

A pointer to the variable that receives a pointer to the byte array containing the output data. The buffer is allocated by the COM interface to store the output data. The caller is responsible for calling <a href="_com_cotaskmemfree">CoTaskMemFree</a> to free the buffer.


### -param uSize [out]

A pointer to a variable that receives the size of the byte array specified by **ppData.


## -returns
The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation was successfully carried out.
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>The interface handle was invalid.
<dl>
<dt><b>E_POINTER</b></dt>
</dl>At least one of the pointer variable parameters did not reference a valid memory location.
<dl>
<dt><b>None of the above</b></dt>
</dl>The <b>HRESULT</b> contains an error code corresponding to the last error.

 


## -remarks
A single bidi request can have multiple results. The application calls <a href="https://msdn.microsoft.com/library/windows/hardware/dd144974">IBidiRequest::GetEnumCount</a> to get the number of results from the bidi request.

If an application calls <b>GetOutputData</b> with the same index twice, the interface allocates two different buffers and thus the application must free both buffers.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>
</dt>
<dt>
<a href="..\bidispl\nn-bidispl-ibidirequest.md">IBidiRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dd144974">IBidiRequest::GetEnumCount</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest::IBidiRequest::GetOutputData method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

