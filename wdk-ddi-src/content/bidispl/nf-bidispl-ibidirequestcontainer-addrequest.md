---
UID: NF:bidispl.IBidiRequestContainer.AddRequest
title: IBidiRequestContainer::AddRequest (bidispl.h)
description: The AddRequest method adds a request to the request list.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiRequestContainer::AddRequest"]
ms.keywords: AddRequest, AddRequest method [Print Devices], AddRequest method [Print Devices],IBidiRequestContainer interface, IBidiRequestContainer interface [Print Devices],AddRequest method, IBidiRequestContainer.AddRequest, IBidiRequestContainer::AddRequest, _win32_IBidiRequestContainer_AddRequest, bidispl/IBidiRequestContainer::AddRequest, gdi.ibidirequestcontainer_ibidirequestcontainer__addrequest, print.ibidirequestcontainer_ibidirequestcontainer__addrequest
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
 - IBidiRequestContainer::AddRequest
 - bidispl/IBidiRequestContainer::AddRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequestContainer::AddRequest
---

## -description

The **AddRequest** method adds a request to the request list.

## -parameters

### -param pRequest [in]

A pointer to the [IBidiRequest](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest) interface.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -remarks

This is similar to adding an item in a link list. In this case, [IBidiRequestContainer](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequestcontainer) will hold a reference to *pRequest* by calling pRequest->AddRef.

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiRequest](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequest)

[IBidiRequestContainer](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequestcontainer)
