---
UID: NF:bidispl.IBidiRequestContainer.GetEnumObject
title: IBidiRequestContainer::GetEnumObject (bidispl.h)
description: The GetEnumObject method enumerates the bidi requests in a list.
old-location: print\ibidirequestcontainer_ibidirequestcontainer__getenumobject.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IBidiRequestContainer::GetEnumObject"]
ms.keywords: GetEnumObject, GetEnumObject method [Print Devices], GetEnumObject method [Print Devices],IBidiRequestContainer interface, IBidiRequestContainer interface [Print Devices],GetEnumObject method, IBidiRequestContainer.GetEnumObject, IBidiRequestContainer::GetEnumObject, _win32_IBidiRequestContainer_GetEnumObject, bidispl/IBidiRequestContainer::GetEnumObject, gdi.ibidirequestcontainer_ibidirequestcontainer__getenumobject, print.ibidirequestcontainer_ibidirequestcontainer__getenumobject
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
 - IBidiRequestContainer::GetEnumObject
 - bidispl/IBidiRequestContainer::GetEnumObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequestContainer.GetEnumObject
---

# IBidiRequestContainer::GetEnumObject


## -description

The <b>GetEnumObject</b> method enumerates the bidi requests in a list.

## -parameters

### -param ppenum 

[out]
Pointer to the variable that receives a pointer to the <a href="/windows/win32/api/objidl/nn-objidl-ienumunknown">IEnumUnknown</a> interface that enumerates the bidi requests in the container.

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

## -remarks

An application can call <a href="/windows/win32/api/objidl/nf-objidl-ienumunknown-next">IEnumUnknown::Next</a> to retrieve one or more <a href="/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest">IBidiRequest</a> interfaces.

## -see-also

<a href="/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequestcontainer">IBidiRequestContainer</a>



<a href="/windows/win32/api/objidl/nn-objidl-ienumunknown">IEnumUnknown</a>
