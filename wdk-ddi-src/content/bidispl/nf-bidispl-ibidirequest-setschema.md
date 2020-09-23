---
UID: NF:bidispl.IBidiRequest.SetSchema
title: IBidiRequest::SetSchema (bidispl.h)
description: The SetSchema method sets the bidi schema string.
old-location: print\ibidirequest_ibidirequest__setschema.htm
tech.root: print
ms.assetid: ca4f7ea4-fcad-42b0-a63a-eee3706e5cbf
ms.date: 04/20/2018
keywords: ["IBidiRequest::SetSchema"]
ms.keywords: IBidiRequest interface [Print Devices],SetSchema method, IBidiRequest.SetSchema, IBidiRequest::SetSchema, SetSchema, SetSchema method [Print Devices], SetSchema method [Print Devices],IBidiRequest interface, _win32_IBidiRequest_SetSchema, bidispl/IBidiRequest::SetSchema, gdi.ibidirequest_ibidirequest__setschema, print.ibidirequest_ibidirequest__setschema
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
 - IBidiRequest::SetSchema
 - bidispl/IBidiRequest::SetSchema
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequest.SetSchema
---

# IBidiRequest::SetSchema


## -description

The <b>SetSchema</b> method sets the bidi schema string.

## -parameters

### -param pszSchema 

[in]
Pointer to a schema string.

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

## -see-also

<a href="/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest">IBidiRequest</a>