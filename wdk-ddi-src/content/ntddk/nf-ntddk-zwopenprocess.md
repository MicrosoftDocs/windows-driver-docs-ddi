---
UID: NF:ntddk.ZwOpenProcess
title: ZwOpenProcess function (ntddk.h)
description: Learn how the ZwOpenProcess routine opens a handle to a process object and sets the access rights to this object.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["ZwOpenProcess function"]
ms.keywords: NtOpenProcess, ZwOpenProcess, ZwOpenProcess routine [Kernel-Mode Driver Architecture], k111_cf01d6cd-b10e-46b6-9b78-984aac1ef96d.xml, kernel.zwopenprocess, ntddk/NtOpenProcess, ntddk/ZwOpenProcess
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
 - ZwOpenProcess
 - ntddk/ZwOpenProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenProcess
---

## -description

The **ZwOpenProcess** routine opens a handle to a process object and sets the access rights to this object.

## -parameters

### -param ProcessHandle [out]

A pointer to a variable of type HANDLE. The **ZwOpenProcess** routine writes the process handle to the variable that this parameter points to.

### -param DesiredAccess [in]

An [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that contains the access rights that the caller has requested to the process object.

### -param ObjectAttributes [in]

A pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies the attributes to apply to the process object handle. The **ObjectName** field of this structure must be set to **NULL**. For more information, see the following Remarks section.

### -param ClientId [in, optional]

A pointer to a client ID that identifies the thread whose process is to be opened. This parameter must be a non-**NULL** pointer to a valid client ID. For more information, see the following Remarks section.

## -returns

**ZwOpenProcess** returns STATUS_SUCCESS if the call is successful. Possible return values include the following error status codes.

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER_MIX** | The caller either supplied an object name or failed to supply a client ID. |
| **STATUS_INVALID_CID** | The specified client ID is not valid. |
| **STATUS_INVALID_PARAMETER** | The requested access rights are not valid for a process object. |
| **STATUS_ACCESS_DENIED** | The requested access rights cannot be granted. |

## -remarks

The *ClientId* parameter must point to a client ID that identifies the thread whose process is to be opened. In addition, the **ObjectName** field of the structure pointed to by *ObjectAttributes* must be set to **NULL**.

If the call to this function occurs in user mode, you should use the name "**NtOpenProcess**" instead of "**ZwOpenProcess**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)
