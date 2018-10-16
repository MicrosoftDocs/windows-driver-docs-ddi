---
UID: NF:wdfdriver.WdfDriverRetrieveDriverDataDirectoryString
title: WdfDriverRetrieveDriverDataDirectoryString function
author: windows-driver-content
description:
ms.assetid: 274dd0ee-3714-4c2c-ba44-ab4513520f73
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: WdfDriverRetrieveDriverDataDirectoryString
req.header: wdfdriver.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver: 2.27
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
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	WdfDriverRetrieveDriverDataDirectoryString
product: Windows
targetos: Windows


---

# WdfDriverRetrieveDriverDataDirectoryString function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The **WdfDriverRetrieveDriverDataDirectoryString** method returns a path to a directory on disk in which the driver can store information.  The files in that directory apply to a specific framework driver object.

## -parameters

### -param Driver
[_In_] A handle to the driver's framework driver object that the driver obtained from a previous call to [**WdfDriverCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nf-wdfdriver-wdfdrivercreate) or [**WdfDeviceGetDriver**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicegetdriver).

### -param String
[_In_] A handle to a framework string object that the driver obtained from a previous call to [**WdfStringCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfstring/nf-wdfstring-wdfstringcreate). The framework assigns the fully qualified path of the requested driver directory to the string object.

## -returns
**WdfDriverRetrieveDriverDataDirectoryString** returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method returns an appropriate NTSTATUS error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks
To achieve the same result, a KMDF driver should call [**IoGetDriverDirectory**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdriverdirectory) instead.

For more information about string objects, see [Using String Objects](https://docs.microsoft.com//windows-hardware/drivers/wdf/using-string-objects).

#### Examples

The following code example shows how to call **WdfDriverRetrieveDriverDataDirectoryString**:

```cpp
NTSTATUS status;
WDFSTRING string;

status = WdfStringCreate(
                         NULL,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &string
                         );
if (NT_SUCCESS(status)) {
    status = WdfDriverRetrieveDriverDataDirectoryString(
                         Driver,
                         string
                         );
    if (!NT_SUCCESS(status)) {
        return status;
    }
}
```

## -see-also

[**IoGetDriverDirectory**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdriverdirectory)

[_DRIVER_DIRECTORY_TYPE Enumeration](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_driver_directory_type)
