---
UID: NF:ntifs.IoEnumerateDeviceObjectList
title: IoEnumerateDeviceObjectList function (ntifs.h)
description: Learn more about the IoEnumerateDeviceObjectList routine.
old-location: ifsk\ioenumeratedeviceobjectlist.htm
tech.root: ifsk
ms.date: 01/25/2023
keywords: ["IoEnumerateDeviceObjectList function"]
ms.keywords: IoEnumerateDeviceObjectList, IoEnumerateDeviceObjectList routine [Installable File System Drivers], ifsk.ioenumeratedeviceobjectlist, ioref_5bfd9f2c-73c0-4f69-8a5e-4cc105c2f92a.xml, ntifs/IoEnumerateDeviceObjectList
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000 SP4 Update Rollup; Windows XP
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoEnumerateDeviceObjectList
 - ntifs/IoEnumerateDeviceObjectList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoEnumerateDeviceObjectList
---

# IoEnumerateDeviceObjectList function

## -description

The **IoEnumerateDeviceObjectList** routine enumerates a driver's device object list.

## -parameters

### -param DriverObject [in]

A pointer to the driver object for the driver.

### -param DeviceObjectList [out]

A pointer to a caller-allocated array that receives the device object pointers. This array must be allocated from nonpaged pool. This parameter can be NULL. See Remarks.

### -param DeviceObjectListSize [in]

Size, in bytes, of the **DeviceObjectList** array. This parameter can be zero. See Remarks.

### -param ActualNumberDeviceObjects [out]

Actual number of device objects found in the driver object's device object list. Note that if the array at **DeviceObjectList** is too small, the number of device object pointers that are copied into the array will be less than **ActualNumberDeviceObjects**.

## -returns

**IoEnumerateDeviceObjectList** returns an NTSTATUS code such as one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS          | The call to **IoEnumerateDeviceObjectList** completed successfully. |
| STATUS_BUFFER_TOO_SMALL | The array at **DeviceObjectList** is too small to hold the entire device object list. In this case, **IoEnumerateDeviceObjectList** copies as many device object pointers into the array as possible. |

## -remarks

A file system filter driver calls **IoEnumerateDeviceObjectList** to enumerate:

* The device objects it has created. This is commonly done when the driver is preparing to unload. Note that a filter driver cannot safely be unloaded from a running system. For more information, see [**ZwUnloadDriver**](../wdm/nf-wdm-zwunloaddriver.md).

* The device objects created by the base file system, so the filter knows the number of volumes to which it can attach.

**IoEnumerateDeviceObjectList** returns all device objects created by the filter driver. This includes control device objects (CDOs) as well as volume device objects (VDOs). The two types of device objects can be distinguished by the fact that, by convention, CDOs are named and VDOs are not.

In the latter case, the filter driver typically calls **IoEnumerateDeviceObjectList** twice: once to get the number of device objects in the list, and once to get the device object list itself. In the first call, the caller should set the **DeviceObjectList** parameter to NULL and **DeviceObjectListSize** to zero. In the second call, **DeviceObjectList** should contain a pointer to an appropriately-sized pointer array, and **DeviceObjectListSize** should contain the size, in bytes, of that array.

**IoEnumerateDeviceObjectList** increments the reference count on every device object in the list pointed to by **DeviceObjectList**. Thus every successful call to **IoEnumerateDeviceObjectList** must be matched by a subsequent call to [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md) for each device object in the list. Failure to do so prevents the system from freeing or deleting these device objects because of an outstanding reference count.

## -see-also

[**ExAllocatePool2**](../wdm/nf-wdm-exallocatepool2.md)

[**ExAllocatePool3**](../wdm/nf-wdm-exallocatepool3.md)

[**IoGetAttachedDevice**](nf-ntifs-iogetattacheddevice.md)

[**IoGetAttachedDeviceReference**](nf-ntifs-iogetattacheddevicereference.md)

[**IoGetLowerDeviceObject**](nf-ntifs-iogetlowerdeviceobject.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)

[**ZwUnloadDriver**](../wdm/nf-wdm-zwunloaddriver.md)
