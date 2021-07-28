---
UID: NC:storport.HW_STATE_CHANGE
title: HW_STATE_CHANGE (storport.h)
description: A miniport-provided callback that is called after a notification from StorPortStateChangeDetected is processed.
old-location: storage\hwstorstatechange.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_STATE_CHANGE callback function"]
ms.keywords: HW_STATE_CHANGE, HwStorStateChange, HwStorStateChange routine [Storage Devices], storage.hwstorstatechange, storport/HwStorStateChange
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
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
req.dll: 
req.irql: DISPATCH
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_STATE_CHANGE
 - storport/HW_STATE_CHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - storport.h
api_name:
 - HW_STATE_CHANGE
---

# HW_STATE_CHANGE callback function

## -description

A miniport-provided callback that is called after a notification from [**StorPortStateChangeDetected**](nf-storport-storportstatechangedetected.md) is processed.

## -parameters

### -param HwDeviceExtension

### -param Context

[in, optional] The context supplied as **HwStateChangeContext** by the miniport in the call to [**StorPortStateChangeDetected**](nf-storport-storportstatechangedetected.md).

### -param AddressType

[in] The type of the address in **Address**.

### -param Address

[in]
A pointer to a [**STOR_ADDRESS**](../scsi/ns-scsi-_stor_address.md) structure for the entity whose state change was processed.

### -param Status

[in] The processing status for the state change notification.

#### - DeviceExtension

[in] A pointer to the miniport driver's per-HBA storage area.

## -remarks

The **HwStorStateChange** is called with the StartIo lock acquired by Storport.

This callback enables miniports to do any additional processing that is needed after hardware addition or removal. If a hardware change occurs on the HBA port or bus, the miniport can call [**StorPortStateChangeDetected**](nf-storport-storportstatechangedetected.md) to alert the system of the event.

If the value for **Status** is  < 0x80000000, then the notification processing was successful. Otherwise, the notification process failed.

The name **HwStorStateChange** is just a placeholder for the miniport function that is pointed to by the **HwStateChange** parameter of [**StorPortStateChangeDetected**](nf-storport-storportstatechangedetected.md). The actual prototype of this routine is defined in *Storport.h* as follows:

``` c
typedef
VOID
HW_STATE_CHANGE (
    _In_ PVOID HwDeviceExtension,
    _In_opt_ PVOID Context,
    _In_ SHORT AddressType,
    _In_ PVOID Address,
    _In_ ULONG Status
    );
```

## -see-also

[**STOR_ADDRESS**](../scsi/ns-scsi-_stor_address.md)

[**StorPortStateChangeDetected**](nf-storport-storportstatechangedetected.md)
