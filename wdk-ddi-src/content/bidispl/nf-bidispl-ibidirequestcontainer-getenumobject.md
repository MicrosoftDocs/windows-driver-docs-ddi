---
UID: NF:bidispl.IBidiRequestContainer.GetEnumObject
title: IBidiRequestContainer::GetEnumObject (bidispl.h)
description: The GetEnumObject method enumerates the bidi requests in a list.
tech.root: print
ms.date: 03/03/2023
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
 - IBidiRequestContainer::GetEnumObject
---

## -description

The **GetEnumObject** method enumerates the bidi requests in a list.

## -parameters

### -param ppenum [out]

Pointer to the variable that receives a pointer to the [IEnumUnknown](/windows/win32/api/objidl/nn-objidl-ienumunknown) interface that enumerates the bidi requests in the container.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -remarks

An application can call [IEnumUnknown::Next](/windows/win32/api/objidl/nf-objidl-ienumunknown-next) to retrieve one or more [IBidiRequest](./nn-bidispl-ibidirequest.md) interfaces.

## -see-also

[Bidirectional Communication Interfaces](../_print/index.md)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiRequestContainer](./nn-bidispl-ibidirequestcontainer.md)

[IEnumUnknown](/windows/win32/api/objidl/nn-objidl-ienumunknown)