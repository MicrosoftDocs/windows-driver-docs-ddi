---
UID: NF:wdfdevice.WdfDeviceRetrieveDeviceDirectoryString
title: WdfDeviceRetrieveDeviceDirectoryString function
description:
ms.assetid: 94f803e2-0972-4248-8b55-c02fd096a1e2
ms.date: 10/19/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	WdfDeviceRetrieveDeviceDirectoryString
product:
-	Windows
targetos: Windows

---

# WdfDeviceRetrieveDeviceDirectoryString function


## -description

**WdfDeviceRetrieveDeviceDirectoryString** provides a path to a location on disk that can be used to persist information across reboots. 

## -parameters

### -param Device
[_In_] A handle to a framework device object.

### -param String
[_In_] A handle to a [framework string object](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-string-objects). The framework will assign the directory path to the string object on successful return.

## -returns
This function returns NTSTATUS.
**WdfDeviceRetrieveDeviceDirectoryString** returns STATUS_SUCCESS if the operation succeeds. 

## -remarks
UMDF only. KMDF drivers should use [**IoGetDeviceDirectory**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdevicedirectory).

## -see-also
For info about string objects, see [Using String Objects](https://docs.microsoft.com//windows-hardware/drivers/wdf/using-string-objects).
