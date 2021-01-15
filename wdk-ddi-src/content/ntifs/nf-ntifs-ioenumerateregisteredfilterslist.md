---
UID: NF:ntifs.IoEnumerateRegisteredFiltersList
title: IoEnumerateRegisteredFiltersList function (ntifs.h)
description: The IoEnumerateRegisteredFiltersList routine enumerates the file system filter drivers that have registered with the system.
old-location: ifsk\ioenumerateregisteredfilterslist.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IoEnumerateRegisteredFiltersList function"]
ms.keywords: IoEnumerateRegisteredFiltersList, IoEnumerateRegisteredFiltersList routine [Installable File System Drivers], ifsk.ioenumerateregisteredfilterslist, ioref_b1530889-7d8a-4fd7-a7d3-954b1c7012ca.xml, ntifs/IoEnumerateRegisteredFiltersList
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows Server 2003 Service Pack 1 (SP1) and later.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoEnumerateRegisteredFiltersList
 - ntifs/IoEnumerateRegisteredFiltersList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoEnumerateRegisteredFiltersList
---

# IoEnumerateRegisteredFiltersList function

## -description

The **IoEnumerateRegisteredFiltersList** routine enumerates the file system filter drivers that have registered with the system.

## -parameters

### -param DriverObjectList

[out] A pointer to a caller-allocated array that receives the driver object pointers. This parameter is optional and can be **NULL**. (See the following Remarks section.)

### -param DriverObjectListSize

[in] Size, in bytes, of the *DriverObjectList* array. Can be zero. (See the following Remarks section.)

### -param ActualNumberDriverObjects

[out] Actual number of driver objects found. Note that if the array at *DriverObjectList* is too small, the number of driver object pointers that are copied into the array will be less than *ActualNumberDriverObjects*.

## -returns

**IoEnumerateRegisteredFiltersList** can return one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The call to **IoEnumerateRegisteredFiltersList** was successful. |
| STATUS_BUFFER_TOO_SMALL | The array at *DriverObjectList* is too small to hold the entire driver object list. In this case, **IoEnumerateRegisteredFiltersList** copies as many driver object pointers into the array as possible. |

## -remarks

A file system filter driver calls **IoEnumerateRegisteredFiltersList** to obtain an array of pointers to the driver objects for all file system filter drivers that have called [**IoRegisterFsRegistrationChange**](nf-ntifs-ioregisterfsregistrationchange.md).

The filter drivers are enumerated in order of decreasing distance from the base file system. The first element (index zero) in the *DriverObjectList* array represents the filter that is attached farthest from the file system. The second entry is for the next-farthest filter, and so on. The last entry in the array is for the filter that is closest to the base file system.

**IoEnumerateRegisteredFiltersList** enumerates only legacy filter drivers; it does not enumerate minifilters. To enumerate both minifilters and legacy filters, or only minifilters, call [**FltEnumerateFilterInformation**](../fltkernel/nf-fltkernel-fltenumeratefilterinformation.md).

The filter driver typically calls **IoEnumerateRegisteredFiltersList** twice: once to get the number of driver objects in the list, and once to get the driver object list itself. In the first call, the caller should set the *DriverObjectList* parameter to **NULL** and *DriverObjectListSize* to zero. In the second call, *DriverObjectList* should contain a pointer to an appropriately-sized pointer array, and *DriverObjectListSize* should contain the size, in bytes, of that array.

**IoEnumerateRegisteredFiltersList** increments the reference count on every driver object in the list pointed to by *DriverObjectList*. Thus every successful call to **IoEnumerateRegisteredFiltersList** must be matched by a subsequent call to [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md) for each driver object in the list. Failure to do so prevents the system from freeing or deleting these driver objects because of an outstanding reference count.

Minifilters should call [**FltEnumerateFilterInformation**](../fltkernel/nf-fltkernel-fltenumeratefilterinformation.md) or [**FltEnumerateFilters**](../fltkernel/nf-fltkernel-fltenumeratefilters.md) instead of **IoEnumerateRegisteredFiltersList**.

## -see-also

[**FltEnumerateFilterInformation**](../fltkernel/nf-fltkernel-fltenumeratefilterinformation.md)

[**FltEnumerateFilters**](../fltkernel/nf-fltkernel-fltenumeratefilters.md)

[**IoRegisterFsRegistrationChange**](nf-ntifs-ioregisterfsregistrationchange.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)
