---
UID: NF:bidispl.IBidiSpl2.UnbindDevice
title: IBidiSpl2::UnbindDevice (bidispl.h)
description: The UnbindDevice method releases a printer from a bidirectional printer communication (bidi communication) request.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl2::UnbindDevice"]
ms.keywords: IBidiSpl2 interface [Print Devices],UnbindDevice method, IBidiSpl2.UnbindDevice, IBidiSpl2::UnbindDevice, UnbindDevice, UnbindDevice method [Print Devices], UnbindDevice method [Print Devices],IBidiSpl2 interface, _win32_IBidiSpl2_UnbindDevice, bidispl/IBidiSpl2::UnbindDevice, gdi.ibidispl2_ibidispl2__unbinddevice, print.ibidispl2_ibidispl2__unbinddevice
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
 - IBidiSpl2::UnbindDevice
 - bidispl/IBidiSpl2::UnbindDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl2::UnbindDevice
---

# IBidiSpl2::UnbindDevice

## -description

The **UnbindDevice** method releases a printer from a bidirectional printer communication (bidi communication) request.

## -returns

The method returns one of the following values.

| Value | Description |
|---|---|
| **S_OK** | The operation was successful. |
| **E_HANDLE** | The interface handle is invalid. |
| **None of the above** | The **HRESULT** contains an error code that corresponds to the last error. |

## -see-also

[Bidirectional Communication Interfaces](/windows-hardware/drivers/ddi/_print/index)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiSpl2](/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl2)

[Print Spooler Components](/windows-hardware/drivers/print/print-spooler-components)
