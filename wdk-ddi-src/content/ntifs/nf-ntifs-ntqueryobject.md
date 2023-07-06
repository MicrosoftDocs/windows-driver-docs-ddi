---
UID: NF:ntifs.NtQueryObject
title: NtQueryObject function (ntifs.h)
description: The NtQueryObject routine provides information about a supplied object. If the call occurs in user mode, use the name NtQueryObject.
old-location: kernel\zwqueryobject.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["NtQueryObject function"]
ms.keywords: NtQueryObject, ZwQueryObject, ZwQueryObject routine [Kernel-Mode Driver Architecture], k111_54a1efe7-3cf8-46b3-bbb5-9e7520ba459d.xml, kernel.zwqueryobject, ntifs/NtQueryObject, ntifs/ZwQueryObject
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NtQueryObject
 - ntifs/NtQueryObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtQueryObject
---

# NtQueryObject function

## -description

The **NtQueryObject** routine provides information about a supplied object.

## -parameters

### -param Handle [in, optional]

A handle to the object to obtain information about.

### -param ObjectInformationClass [in]

Specifies an [**OBJECT_INFORMATION_CLASS**](ne-ntifs-_object_information_class.md) value that determines the type of information returned in the **ObjectInformation** buffer.

### -param ObjectInformation [out, optional]

A pointer to a caller-allocated buffer that receives the requested information.

### -param ObjectInformationLength [in]

Specifies the size, in bytes, of the **ObjectInformation** buffer.

### -param ReturnLength [out, optional]

A pointer to a variable that receives the size, in bytes, of the requested key information. If **NtQueryObject** returns STATUS_SUCCESS, the variable contains the amount of data returned. If **NtQueryObject** returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, you can use the value of the variable to determine the required buffer size.

## -returns

**NtQueryObject** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED        | There were insufficient permissions to perform this query. |
| STATUS_INVALID_HANDLE       | The supplied object handle is invalid. |
| STATUS_INFO_LENGTH_MISMATCH | The info length is not sufficient to hold the data. |

## -remarks

If the call to the **NtQueryObject** function occurs in user mode, you should use the name "**NtQueryObject**" instead of "**ZwQueryObject**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**OBJECT_INFORMATION_CLASS**](ne-ntifs-_object_information_class.md)

[**PUBLIC_OBJECT_BASIC_INFORMATION**](ns-ntifs-_public_object_basic_information.md)

[**PUBLIC_OBJECT_TYPE_INFORMATION**](ns-ntifs-__public_object_type_information.md)
