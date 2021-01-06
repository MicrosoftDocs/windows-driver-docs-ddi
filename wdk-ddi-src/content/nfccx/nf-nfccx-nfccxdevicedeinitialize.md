---
UID: NF:nfccx.NfcCxDeviceDeinitialize
title: NfcCxDeviceDeinitialize function (nfccx.h)
description: Called by the client driver after a WDF device has been created during the AddDevice routine.
old-location: nfpdrivers\_nfccxdevicedeinitialize.htm
tech.root: nfpdrivers
ms.date: 02/15/2018
keywords: ["NfcCxDeviceDeinitialize function"]
ms.keywords: NfcCxDeviceDeinitialize, NfcCxDeviceDeinitialize method [Near-Field Proximity Drivers], nfccx/NfcCxDeviceDeinitialize, nfpdrivers._nfccxdevicedeinitialize
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Nfccsstub.lib
req.dll: NfcCx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - NfcCxDeviceDeinitialize
 - nfccx/NfcCxDeviceDeinitialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NfcCx.dll
api_name:
 - NfcCxDeviceDeinitialize
---

# NfcCxDeviceDeinitialize function


## -description

Called by the client driver after a WDF device has been created during the AddDevice routine.

## -parameters

### -param Device

A handle to a framework device object.

## -returns

If the operation succeeds, the function returns STATUS_SUCCESS.

## -see-also

<a href="/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) design guide</a>
