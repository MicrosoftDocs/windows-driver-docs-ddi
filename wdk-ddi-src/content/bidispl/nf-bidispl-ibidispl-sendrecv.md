---
UID: NF:bidispl.IBidiSpl.SendRecv
title: IBidiSpl::SendRecv (bidispl.h)
description: The SendRecv method sends a bidi request to the printer.
old-location: print\ibidispl_ibidispl__sendrecv.htm
tech.root: print
ms.assetid: 0c91abd0-5e49-4e23-a50f-9d1dacf9d868
ms.date: 04/20/2018
keywords: ["IBidiSpl::SendRecv"]
ms.keywords: IBidiSpl interface [Print Devices],SendRecv method, IBidiSpl.SendRecv, IBidiSpl::SendRecv, SendRecv, SendRecv method [Print Devices], SendRecv method [Print Devices],IBidiSpl interface, _win32_IBidiSpl_SendRecv, bidispl/IBidiSpl::SendRecv, gdi.ibidispl_ibidispl__sendrecv, print.ibidispl_ibidispl__sendrecv
f1_keywords:
 - "bidispl/IBidiSpl.SendRecv"
 - "IBidiSpl.SendRecv"
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
- IBidiSpl.SendRecv
targetos: Windows
req.typenames: 
---

# IBidiSpl::SendRecv


## -description


The <b>SendRecv</b> method sends a bidi request to the printer.


## -parameters




### -param pszAction 
[in]
A pointer to a NULL-terminated string that specifies the action for this bidi request. It can be one of the following constants.

<table>
<tr>
<th>Constant</th>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>BIDI_ACTION_ENUM_SCHEMA</td>
<td>L"EnumSchema"</td>
<td>Enumerate the schema. The returned data will be a list of schema that the port monitor or print provider supports.</td>
</tr>
<tr>
<td>BIDI_ACTION_GET</td>
<td>L"Get"</td>
<td>Get the value of a specified schema. </td>
</tr>
<tr>
<td>BIDI_ACTION_GET_ALL</td>
<td>L"GetAll"</td>
<td>Get the values of all child nodes of the specified schema.</td>
</tr>
<tr>
<td>BIDI_ACTION_SET</td>
<td>L"Set"</td>
<td>Set a value of the schema.</td>
</tr>
<tr>
<td>BIDI_ACTION_GET_WITH_ARGUMENT</td>
<td>L"GetWithArgument"  </td>
<td>Request the bidi schema value using the data set as input argument.</td>
</tr>
</table>
 


### -param pRequest 
[in]
A pointer to a single bidi request.


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
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code corresponding to the last error.

</td>
</tr>
</table>
 

Note that the <b>HRESULT</b> may contain a system error code defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidi-error-codes">Bidi Error Codes</a>.




## -remarks



The BIDI_ACTION_* values are case insensitive strings.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl">IBidiSpl</a>
 

 

