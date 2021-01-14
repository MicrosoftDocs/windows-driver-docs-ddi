---
UID: NF:wdm.ZwEnumerateTransactionObject
title: ZwEnumerateTransactionObject function (wdm.h)
description: The ZwEnumerateTransactionObject routine enumerates the KTM objects on a computer.
old-location: kernel\zwenumeratetransactionobject.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwEnumerateTransactionObject function"]
ms.keywords: NtEnumerateTransactionObject, ZwEnumerateTransactionObject, ZwEnumerateTransactionObject routine [Kernel-Mode Driver Architecture], kernel.zwenumeratetransactionobject, ktm_ref_f9c45fce-5dbe-4dad-9943-3f31fb692c65.xml, wdm/NtEnumerateTransactionObject, wdm/ZwEnumerateTransactionObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
 - ZwEnumerateTransactionObject
 - wdm/ZwEnumerateTransactionObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwEnumerateTransactionObject
---

# ZwEnumerateTransactionObject function


## -description

The <b>ZwEnumerateTransactionObject</b> routine enumerates the <a href="/windows-hardware/drivers/kernel/ktm-objects">KTM objects</a> on a computer.

## -parameters

### -param RootObjectHandle 

[in, optional]
A handle to a KTM object. The routine enumerates the child objects of the specified object. This parameter is optional and can be <b>NULL</b>. For more information about valid values for this parameter, see the table in the following Remarks section.

### -param QueryType 

[in]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_ktmobject_type">KTMOBJECT_TYPE</a>-typed value that identifies the object type to enumerate. For more information about valid values for this parameter, see the table in the following Remarks section.

### -param ObjectCursor 

[in, out]
A pointer to a caller-allocated buffer that begins with a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ktmobject_cursor">KTMOBJECT_CURSOR</a> structure. <b>ZwEnumerateTransactionObject</b> uses the buffer to store the GUIDs of objects that it finds.

### -param ObjectCursorLength 

[in]
The length, in bytes, of the buffer that <i>ObjectCursor</i> points to.

### -param ReturnLength 

[out]
A pointer to a caller-allocated location that receives the number of bytes that <b>ZwEnumerateTransactionObject</b> returns in the <i>ObjectCursor</i> buffer, including the length of the <b>KTMOBJECT_CURSOR</b> structure and the length of all returned GUIDs.

## -returns

<b>ZwEnumerateTransactionObject</b> returns STATUS_SUCCESS if the operation succeeds but the routine has not enumerated all the objects. If there are no more objects to enumerate, the routine returns STATUS_NO_MORE_ENTRIES. Otherwise, this routine might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>QueryType</i> or <i>ObjectCursorLength</i> parameter's value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The handle that the <i>RootObjectHandle</i> parameter specifies is not a handle to a valid KTM object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
An object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the objects that are being enumerated.

</td>
</tr>
</table>
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The following table contains the valid values for the <i>RootObjectHandle</i> and <i>QueryType</i> parameters.

<table>
<tr>
<th><i>QueryType</i> parameter</th>
<th><i>RootObjectHandle</i> parameter</th>
<th>Objects enumerated</th>
</tr>
<tr>
<td>
KTMOBJECT_TRANSACTION_MANAGER

</td>
<td>
<b>NULL</b>

</td>
<td>
All transaction manager objects

</td>
</tr>
<tr>
<td>
KTMOBJECT_RESOURCE_MANAGER

</td>
<td>
A handle to a transaction manager object.

The handle must have TRANSACTIONMANAGER_QUERY_INFORMATION access to the object.

</td>
<td>
All resource manager objects that belong to the specified transaction manager object

</td>
</tr>
<tr>
<td>
KTMOBJECT_ENLISTMENT

</td>
<td>
A handle to a resource manager object.

The handle must have RESOURCEMANAGER_QUERY_INFORMATION access to the object.

</td>
<td>
All enlistment objects that belong to the specified resource manager object

</td>
</tr>
<tr>
<td>
KTMOBJECT_TRANSACTION

</td>
<td>
A handle to a transaction manager object.

The handle must have TRANSACTIONMANAGER_QUERY_INFORMATION access to the object.

</td>
<td>
All transaction objects that belong to the specified transaction manager object

</td>
</tr>
<tr>
<td>
KTMOBJECT_TRANSACTION

</td>
<td>
<b>NULL</b>

</td>
<td>
All transaction objects that belong to all transaction manager objects

</td>
</tr>
</table>
 

Most TPS components do not have to call <b>ZwEnumerateTransactionObject</b>, but the routine might be useful if you have to write a debugging utility.

Before your component calls <b>ZwEnumerateTransactionObject</b>, it must allocate and zero the buffer that <i>ObjectCursor</i> points to. The buffer's GUID array can be large enough to receive one or more elements. 

To enumerate all of the <a href="/windows-hardware/drivers/kernel/ktm-objects">KTM objects</a> of the specified type, your component must call <b>ZwEnumerateTransactionObject</b> repeatedly until it returns STATUS_NO_MORE_ENTRIES. 

Every time that the routine is called, it fills the buffer's GUID array with as many object GUIDs that will fit. After each call, your component can use the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ktmobject_cursor">KTMOBJECT_CURSOR</a> structure's <b>ObjectIdCount</b> member to determine the number of object GUIDs that the routine stored in the array.

<b>NtEnumerateTransactionObject</b> and <b>ZwEnumerateTransactionObject</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.


#### Examples

The following code example shows how to enumerate all of the transaction objects on a computer. In this example, the <b>KTMOBJECT_CURSOR</b> structure's GUID array contains only one element, so each call to <b>ZwEnumerateTransactionObject</b> returns one GUID. The routine creates a Unicode string from the GUID and displays the string.


```
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

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ktmobject_cursor">KTMOBJECT_CURSOR</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_ktmobject_type">KTMOBJECT_TYPE</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>

