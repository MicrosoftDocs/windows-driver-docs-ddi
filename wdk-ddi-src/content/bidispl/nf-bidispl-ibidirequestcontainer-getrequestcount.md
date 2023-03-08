---
UID: NF:bidispl.IBidiRequestContainer.GetRequestCount
title: IBidiRequestContainer::GetRequestCount (bidispl.h)
description: The GetRequestCount method gets the number of requests in the request list.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiRequestContainer::GetRequestCount"]
ms.keywords: GetRequestCount, GetRequestCount method [Print Devices], GetRequestCount method [Print Devices],IBidiRequestContainer interface, IBidiRequestContainer interface [Print Devices],GetRequestCount method, IBidiRequestContainer.GetRequestCount, IBidiRequestContainer::GetRequestCount, _win32_IBidiRequestContainer_GetRequestCount, bidispl/IBidiRequestContainer::GetRequestCount, gdi.ibidirequestcontainer_ibidirequestcontainer__getrequestcount, print.ibidirequestcontainer_ibidirequestcontainer__getrequestcount
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
 - IBidiRequestContainer::GetRequestCount
 - bidispl/IBidiRequestContainer::GetRequestCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiRequestContainer::GetRequestCount
---

## -description

The **GetRequestCount** method gets the number of requests in the request list.

## -parameters

### -param puCount [out]

Pointer to a variable that receives the number of requests.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiRequestContainer](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidirequestcontainer)
