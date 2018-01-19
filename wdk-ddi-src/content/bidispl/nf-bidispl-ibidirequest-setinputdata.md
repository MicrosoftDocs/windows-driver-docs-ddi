---
UID: NF:bidispl.IBidiRequest.SetInputData
title: IBidiRequest::SetInputData method
author: windows-driver-content
description: The IBidiRequest::SetInputData method sets the data to send to the printer.
old-location: print\ibidirequest_ibidirequest__setinputdata.htm
old-project: print
ms.assetid: 8db7b5cd-b03f-4973-8711-8ac022bfb2b5
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IBidiRequest, IBidiRequest::SetInputData, SetInputData
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
req.alt-api: IBidiRequest.IBidiRequest::SetInputData
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

# IBidiRequest::SetInputData method



## -description
The <b>IBidiRequest::SetInputData</b> method sets the data to send to the printer.



## -syntax

````
HRESULT IBidiRequest::SetInputData(
  [in] const DWORD dwType,
  [in] const BYTE  *pData,
  [in] const UINT  uSize
);
````


## -parameters

### -param dwType [in]

The type of data to be sent. This parameter can be one of the following values.

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
 


### -param pData [in]

A pointer to the byte array that contains the data. For example, if <i>dwType</i> is BIDI_BOOL, <i>pData</i> points to a buffer that contains a Boolean value and if <i>dwType</i> is BIDI_BLOB, <i>pData</i> points to a buffer that contains the binary data.


### -param uSize [in]

Size, in bytes, of the byte array specified by <i>pData</i>.


## -returns
The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation was successfully carried out.
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>The interface handle was invalid.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The type of the data was not consistent with its size.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>Memory allocation failed.
<dl>
<dt><b>None of the above</b></dt>
</dl>The <b>HRESULT</b> contains an error code corresponding to the last error.

 


## -remarks
If an application calls <b>SetInputData</b> more than once, only the value of the last call will be set.


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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest::IBidiRequest::SetInputData method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

