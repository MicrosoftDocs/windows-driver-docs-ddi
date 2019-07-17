---
UID: NF:bidispl.IBidiRequestContainer.GetEnumObject
title: IBidiRequestContainer::GetEnumObject (bidispl.h)
description: The GetEnumObject method enumerates the bidi requests in a list.
old-location: print\ibidirequestcontainer_ibidirequestcontainer__getenumobject.htm
tech.root: print
ms.assetid: 1aa7b934-c56b-4bfb-800e-950e1dbd5ba3
ms.date: 04/20/2018
ms.keywords: GetEnumObject, GetEnumObject method [Print Devices], GetEnumObject method [Print Devices],IBidiRequestContainer interface, IBidiRequestContainer interface [Print Devices],GetEnumObject method, IBidiRequestContainer.GetEnumObject, IBidiRequestContainer::GetEnumObject, _win32_IBidiRequestContainer_GetEnumObject, bidispl/IBidiRequestContainer::GetEnumObject, gdi.ibidirequestcontainer_ibidirequestcontainer__getenumobject, print.ibidirequestcontainer_ibidirequestcontainer__getenumobject
ms.topic: method
f1_keywords:
 - "bidispl/IBidiRequestContainer.GetEnumObject"
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
- IBidiRequestContainer.GetEnumObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequestContainer::GetEnumObject


## -description


The <b>GetEnumObject</b> method enumerates the bidi requests in a list.


## -parameters




### -param ppenum [out]

Pointer to the variable that receives a pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-ienumunknown">IEnumUnknown</a> interface that enumerates the bidi requests in the container.


## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Error Handling</a>.

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



An application can call <a href="https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ienumunknown-next">IEnumUnknown::Next</a> to retrieve one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nn-bidispl-ibidirequest">IBidiRequest</a> interfaces.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nn-bidispl-ibidirequestcontainer">IBidiRequestContainer</a>



<a href="https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-ienumunknown">IEnumUnknown</a>
 

 

