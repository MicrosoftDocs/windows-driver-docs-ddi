---
UID: NF:bidispl.IBidiSpl.BindDevice
title: IBidiSpl::BindDevice (bidispl.h)
description: The BindDevice method binds a printer to a bidi request. This method is similar to the OpenPrinter function.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl::BindDevice"]
ms.keywords: BIDI_ACCESS_ADMINISTRATOR, BIDI_ACCESS_USER, BindDevice, BindDevice method [Print Devices], BindDevice method [Print Devices],IBidiSpl interface, IBidiSpl interface [Print Devices],BindDevice method, IBidiSpl.BindDevice, IBidiSpl::BindDevice, _win32_IBidiSpl_BindDevice, bidispl/IBidiSpl::BindDevice, gdi.ibidispl_ibidispl__binddevice, print.ibidispl_ibidispl__binddevice
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
 - IBidiSpl::BindDevice
 - bidispl/IBidiSpl::BindDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl::BindDevice
---

## -description

The **BindDevice** method binds a printer to a bidi request. This method is similar to the [OpenPrinter](/windows-hardware/drivers/print/openprinter) function.

## -parameters

### -param pszDeviceName [in]

A pointer to a null-terminated string that contains name of the printer or print server. If **NULL**, it indicates the local printer server.

### -param dwAccess [in]

The access privileges for the printer. This parameter can be one of the following values.

| Value | Description |
|---|---|
| BIDI_ACCESS_ADMINISTRATOR | Permits users to perform all administrative tasks and basic printing operations except for SYNCHRONIZE. This is the same as PRINTER_ALL_ACCESS in [OpenPrinter](/windows-hardware/drivers/print/openprinter). |
| BIDI_ACCESS_USER | Permits users to perform basic printing operations. This is the same as PRINTER_ACCESS_USE in [OpenPrinter](/windows-hardware/drivers/print/openprinter). |

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

[OpenPrinter](/windows-hardware/drivers/print/openprinter)