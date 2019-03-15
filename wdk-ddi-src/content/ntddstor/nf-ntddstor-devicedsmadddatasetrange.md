---
UID: NF:ntddstor.DeviceDsmAddDataSetRange
title: DeviceDsmAddDataSetRange function (ntddstor.h)
description: The DeviceDsmAddDataSetRange function adds a data set range to a DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure.
ms.assetid: 22dca47e-9542-486a-bbf3-053cbd3fccd9
ms.date: 04/06/2018
ms.topic: function
ms.keywords: DeviceDsmAddDataSetRange
req.header: ntddstor.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmAddDataSetRange
product:
- Windows
targetos: Windows

---

# DeviceDsmAddDataSetRange function

## -description

The **DeviceDsmAddDataSetRange** function adds a data set range to a [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES**](ns-ntddstor-_device_manage_data_set_attributes.md) structure.

## -parameters

### -param Input

A pointer to the [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES**](ns-ntddstor-_device_manage_data_set_attributes.md) structure to which to add a data set range.

### -param InputLength

The length, in bytes, of the input buffer.

### -param Offset

The offset, in bytes, for the starting offset for the data set range.

### -param Length

The length, in bytes, of the data set range.

## -returns

Returns TRUE if the data set range was successfully added, or FALSE otherwise.

## -remarks

## -see-also
