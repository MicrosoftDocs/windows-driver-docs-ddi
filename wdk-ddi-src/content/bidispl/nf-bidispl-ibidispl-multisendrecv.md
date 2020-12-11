---
UID: NF:bidispl.IBidiSpl.MultiSendRecv
title: IBidiSpl::MultiSendRecv (bidispl.h)
description: The MultiSendRecv method sends a list of bidi requests.
old-location: print\ibidispl_ibidispl__multisendrecv.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IBidiSpl::MultiSendRecv"]
ms.keywords: IBidiSpl interface [Print Devices],MultiSendRecv method, IBidiSpl.MultiSendRecv, IBidiSpl::MultiSendRecv, MultiSendRecv, MultiSendRecv method [Print Devices], MultiSendRecv method [Print Devices],IBidiSpl interface, _win32_IBidiSpl_MultiSendRecv, bidispl/IBidiSpl::MultiSendRecv, gdi.ibidispl_ibidispl__multisendrecv, print.ibidispl_ibidispl__multisendrecv
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
 - IBidiSpl::MultiSendRecv
 - bidispl/IBidiSpl::MultiSendRecv
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl.MultiSendRecv
---

# IBidiSpl::MultiSendRecv


## -description

The <b>MultiSendRecv</b> method sends a list of bidi requests.

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
<td>Set a value of the schema. </td>
</tr>
</table>

### -param pRequestContainer 

[in]
A pointer to the list of bidi requests.

## -returns

The method returns one of the following values. For more information about COM error codes, see <a href="/windows/win32/com/com-error-codes">COM Error Codes</a>.

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
 

Note that the <b>HRESULT</b> may contain a system error code defined in <a href="/windows-hardware/drivers/print/bidi-error-codes">Bidi Error Codes</a>.

## -remarks

The BIDI_ACTION_* values are case insensitive strings.

## -see-also

<a href="/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl">IBidiSpl</a>
