---
UID: NF:bidispl.IBidiSpl.UnbindDevice
title: IBidiSpl::UnbindDevice (bidispl.h)
description: The UnbindDevice method unbinds a printer from a bidi request.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl::UnbindDevice"]
ms.keywords: IBidiSpl interface [Print Devices],UnbindDevice method, IBidiSpl.UnbindDevice, IBidiSpl::UnbindDevice, UnbindDevice, UnbindDevice method [Print Devices], UnbindDevice method [Print Devices],IBidiSpl interface, _win32_IBidiSpl_UnbindDevice, bidispl/IBidiSpl::UnbindDevice, gdi.ibidispl_ibidispl__unbinddevice, print.ibidispl_ibidispl__unbinddevice
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
 - IBidiSpl::UnbindDevice
 - bidispl/IBidiSpl::UnbindDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl::UnbindDevice
---

## -description

The **UnbindDevice** method unbinds a printer from a bidi request.

## -returns

The method returns one of the following values. For more information about COM error codes, see [COM Error Codes](/windows/win32/com/com-error-codes).

| Value | Description |
|---|---|
| **S_OK** | The operation was successfully carried out. |
| **E_HANDLE** | The interface handle was invalid. |
| **None of the above** | The **HRESULT** contains an error code corresponding to the last error. |

## -see-also

[Bidirectional Communication Interfaces](../_print/index.md)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiSpl](./nn-bidispl-ibidispl.md)