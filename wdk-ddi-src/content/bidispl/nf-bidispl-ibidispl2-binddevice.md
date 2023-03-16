---
UID: NF:bidispl.IBidiSpl2.BindDevice
title: IBidiSpl2::BindDevice (bidispl.h)
description: The BindDevice method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the OpenPrinter function.
tech.root: print
ms.date: 03/03/2023
keywords: ["IBidiSpl2::BindDevice"]
ms.keywords: BIDI_ACCESS_ADMINISTRATOR, BIDI_ACCESS_USER, BindDevice, BindDevice method [Print Devices], BindDevice method [Print Devices],IBidiSpl2 interface, IBidiSpl2 interface [Print Devices],BindDevice method, IBidiSpl2.BindDevice, IBidiSpl2::BindDevice, _win32_IBidiSpl2_BindDevice, bidispl/IBidiSpl2::BindDevice, gdi.ibidispl2_ibidispl2__binddevice, print.ibidispl2_ibidispl2__binddevice
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
 - IBidiSpl2::BindDevice
 - bidispl/IBidiSpl2::BindDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bidispl.dll
api_name:
 - IBidiSpl2::BindDevice
---

## -description

The **BindDevice** method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the [OpenPrinter](/windows-hardware/drivers/print/openprinter) function.

## -parameters

### -param pszDeviceName [in]

A pointer to a null-terminated string that contains the name of the printer or print server. If **NULL**, this parameter indicates the local print server.

### -param dwAccess [in]

The access privileges for the printer. This parameter can be one of the following values.

| Value | Description |
|---|---|
| **BIDI_ACCESS_ADMINISTRATOR** | Permits users to perform all administrative tasks and basic printing operations except for SYNCHRONIZE. This is the same as PRINTER_ALL_ACCESS in [OpenPrinter](/windows-hardware/drivers/print/openprinter). |
| **BIDI_ACCESS_USER** | Permits users to perform basic printing operations. This is the same as PRINTER_ACCESS_USE in [OpenPrinter](/windows-hardware/drivers/print/openprinter). |

## -returns

The method returns one of the following values.

| Return code | Description |
|---|---|
| **S_OK** | The operation was successful. |
| **E_HANDLE** | The interface handle is invalid. |
| **None of the above** | The **HRESULT** contains an error code that corresponds to the last error. |

## -see-also

[Bidirectional Communication Interfaces](../_print/index.md)

[Bidirectional Communication Schema](/windows-hardware/drivers/print/bidirectional-communication-schema)

[IBidiSpl2](./nn-bidispl-ibidispl2.md)

[OpenPrinter](/windows-hardware/drivers/print/openprinter)

[Print Spooler Components](/windows-hardware/drivers/print/print-spooler-components)