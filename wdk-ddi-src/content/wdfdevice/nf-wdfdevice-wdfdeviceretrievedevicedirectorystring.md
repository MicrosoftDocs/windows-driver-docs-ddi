---
UID: NF:wdfdevice.WdfDeviceRetrieveDeviceDirectoryString
title: WdfDeviceRetrieveDeviceDirectoryString function (wdfdevice.h)
description: 
tech.root: wdf
ms.date: 10/19/2018
keywords: ["WdfDeviceRetrieveDeviceDirectoryString function"]
ms.keywords: WdfDeviceRetrieveDeviceDirectoryString
req.header: wdfdevice.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.25
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - WdfDeviceRetrieveDeviceDirectoryString
 - wdfdevice/WdfDeviceRetrieveDeviceDirectoryString
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WdfDeviceRetrieveDeviceDirectoryString
---

# WdfDeviceRetrieveDeviceDirectoryString function


## -description

[Applies to UMDF only]

**WdfDeviceRetrieveDeviceDirectoryString** provides a path to a location on disk that can be used to persist information across reboots.

## -parameters

### -param Device

[_In_] A handle to a framework device object.

### -param String

[_In_] A handle to a [framework string object](/windows-hardware/drivers/wdf/using-string-objects). The framework will assign the directory path to the string object on successful return.

## -returns

This function returns NTSTATUS.
**WdfDeviceRetrieveDeviceDirectoryString** returns STATUS_SUCCESS if the operation succeeds.

## -remarks

UMDF only. KMDF drivers should use [**IoGetDeviceDirectory**](../wdm/nf-wdm-iogetdevicedirectory.md).

## -see-also

For info about string objects, see [Using String Objects](/windows-hardware/drivers/wdf/using-string-objects).
