---
UID: NF:wdfdriver.WdfDriverRetrieveDriverDataDirectoryString
title: WdfDriverRetrieveDriverDataDirectoryString function (wdfdriver.h)
description: 
ms.assetid: 274dd0ee-3714-4c2c-ba44-ab4513520f73
ms.date: 10/19/2018
keywords: ["WdfDriverRetrieveDriverDataDirectoryString function"]
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - WdfDriverRetrieveDriverDataDirectoryString
 - wdfdriver/WdfDriverRetrieveDriverDataDirectoryString
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WdfDriverRetrieveDriverDataDirectoryString
---

# WdfDriverRetrieveDriverDataDirectoryString function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The **WdfDriverRetrieveDriverDataDirectoryString** method returns a path to a directory on disk in which the driver can store information.  The files in that directory apply to a specific framework driver object.

## -parameters

### -param Driver

[_In_] A handle to the driver's framework driver object that the driver obtained from a previous call to [**WdfDriverCreate**](./nf-wdfdriver-wdfdrivercreate.md) or [**WdfDeviceGetDriver**](../wdfdevice/nf-wdfdevice-wdfdevicegetdriver.md).

### -param String

[_In_] A handle to a framework string object that the driver obtained from a previous call to [**WdfStringCreate**](../wdfstring/nf-wdfstring-wdfstringcreate.md). The framework assigns the fully qualified path of the requested driver directory to the string object.

## -returns

**WdfDriverRetrieveDriverDataDirectoryString** returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method returns an appropriate NTSTATUS error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

To achieve the same result, a KMDF driver should call [**IoGetDriverDirectory**](../wdm/nf-wdm-iogetdriverdirectory.md) instead.

For more information about string objects, see [Using String Objects](/windows-hardware/drivers/wdf/using-string-objects).

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

[**IoGetDriverDirectory**](../wdm/nf-wdm-iogetdriverdirectory.md)

[_DRIVER_DIRECTORY_TYPE Enumeration](../wdm/ne-wdm-_driver_directory_type.md)