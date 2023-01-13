---
UID: NF:wdm.NtEnumerateTransactionObject
title: NtEnumerateTransactionObject function (wdm.h)
description: The ZwEnumerateTransactionObject routine enumerates the KTM objects on a computer.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["NtEnumerateTransactionObject function"]
ms.keywords: NtEnumerateTransactionObject, ZwEnumerateTransactionObject, ZwEnumerateTransactionObject routine [Kernel-Mode Driver Architecture], kernel.zwenumeratetransactionobject, ktm_ref_f9c45fce-5dbe-4dad-9943-3f31fb692c65.xml, wdm/NtEnumerateTransactionObject, wdm/ZwEnumerateTransactionObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
 - NtEnumerateTransactionObject
 - wdm/NtEnumerateTransactionObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtEnumerateTransactionObject
---

## -description

The **ZwEnumerateTransactionObject** routine enumerates the [KTM objects](/windows-hardware/drivers/kernel/ktm-objects) on a computer.

## -parameters

### -param RootObjectHandle [in, optional]

A handle to a KTM object. The routine enumerates the child objects of the specified object. This parameter is optional and can be **NULL**. For more information about valid values for this parameter, see the table in the following Remarks section.

### -param QueryType [in]

A [KTMOBJECT_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_ktmobject_type)-typed value that identifies the object type to enumerate. For more information about valid values for this parameter, see the table in the following Remarks section.

### -param ObjectCursor [in, out]

A pointer to a caller-allocated buffer that begins with a [**KTMOBJECT_CURSOR**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_ktmobject_cursor) structure. **ZwEnumerateTransactionObject** uses the buffer to store the GUIDs of objects that it finds.

### -param ObjectCursorLength [in]

The length, in bytes, of the buffer that *ObjectCursor* points to.

### -param ReturnLength [out]

A pointer to a caller-allocated location that receives the number of bytes that **ZwEnumerateTransactionObject** returns in the *ObjectCursor* buffer, including the length of the **KTMOBJECT_CURSOR** structure and the length of all returned GUIDs.

## -returns

**ZwEnumerateTransactionObject** returns STATUS_SUCCESS if the operation succeeds but the routine has not enumerated all the objects. If there are no more objects to enumerate, the routine returns STATUS_NO_MORE_ENTRIES. Otherwise, this routine might return one of the following values:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The *QueryType* or *ObjectCursorLength* parameter's value is invalid. |
| **STATUS_OBJECT_TYPE_MISMATCH** | The handle that the *RootObjectHandle* parameter specifies is not a handle to a valid KTM object. |
| **STATUS_INVALID_HANDLE** | An object handle is invalid. |
| **STATUS_ACCESS_DENIED** | The caller does not have appropriate access to the objects that are being enumerated. |

The routine might return other [NTSTATUS values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The following table contains the valid values for the *RootObjectHandle* and *QueryType* parameters.

| *QueryType* parameter | *RootObjectHandle* parameter | Objects enumerated |
|---|---|---|
| KTMOBJECT_TRANSACTION_MANAGER | **NULL** | All transaction manager objects |
| KTMOBJECT_RESOURCE_MANAGER | A handle to a transaction manager object. The handle must have TRANSACTIONMANAGER_QUERY_INFORMATION access to the object. | All resource manager objects that belong to the specified transaction manager object |
| KTMOBJECT_ENLISTMENT | A handle to a resource manager object. The handle must have RESOURCEMANAGER_QUERY_INFORMATION access to the object. | All enlistment objects that belong to the specified resource manager object |
| KTMOBJECT_TRANSACTION | A handle to a transaction manager object. The handle must have TRANSACTIONMANAGER_QUERY_INFORMATION access to the object. | All transaction objects that belong to the specified transaction manager object |
| KTMOBJECT_TRANSACTION | **NULL** | All transaction objects that belong to all transaction manager objects |

Most TPS components do not have to call **ZwEnumerateTransactionObject**, but the routine might be useful if you have to write a debugging utility.

Before your component calls **ZwEnumerateTransactionObject**, it must allocate and zero the buffer that *ObjectCursor* points to. The buffer's GUID array can be large enough to receive one or more elements.

To enumerate all of the [KTM objects](/windows-hardware/drivers/kernel/ktm-objects) of the specified type, your component must call **ZwEnumerateTransactionObject** repeatedly until it returns STATUS_NO_MORE_ENTRIES.

Every time that the routine is called, it fills the buffer's GUID array with as many object GUIDs that will fit. After each call, your component can use the [**KTMOBJECT_CURSOR**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_ktmobject_cursor) structure's **ObjectIdCount** member to determine the number of object GUIDs that the routine stored in the array.

**NtEnumerateTransactionObject** and **ZwEnumerateTransactionObject** are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

### Examples

The following code example shows how to enumerate all of the transaction objects on a computer. In this example, the **KTMOBJECT_CURSOR** structure's GUID array contains only one element, so each call to **ZwEnumerateTransactionObject** returns one GUID. The routine creates a Unicode string from the GUID and displays the string.

```cpp
NTSTATUS Status;
UNICODE_STRING GuidString;
KTMOBJECT_CURSOR Cursor;
ULONG ReturnedBytes;

RtlZeroMemory(&Cursor, sizeof(Cursor));

do {
    Status = ZwEnumerateTransactionObject(
                                          NULL,
                                          KTMOBJECT_TRANSACTION,
                                          &Cursor,
                                          sizeof(Cursor),
                                          &ReturnedBytes
                                          );

    if (Status != STATUS_NO_MORE_ENTRIES) {
        RtlStringFromGUID(
                          &Cursor.ObjectIds[0],
                          &GuidString
                          );
        OutputMessage(GuidString.Buffer);
        OutputMessage(L"\r\n");
        RtlFreeUnicodeString(&GuidString);
    }
} while (Status == STATUS_SUCCESS);
if (Status == STATUS_NO_MORE_ENTRIES) {
    Status = STATUS_SUCCESS;
}
```

## -see-also

[**KTMOBJECT_CURSOR**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_ktmobject_cursor)

[KTMOBJECT_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_ktmobject_type)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)
