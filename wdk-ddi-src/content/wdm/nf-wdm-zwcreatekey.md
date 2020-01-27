---
UID: NF:wdm.ZwCreateKey
title: ZwCreateKey function (wdm.h)
description: The ZwCreateKey routine creates a new registry key or opens an existing one.
old-location: kernel\zwcreatekey.htm
tech.root: kernel
ms.assetid: 333f54e8-738e-4d1f-8fd7-93f282d9b9d8
ms.date: 04/30/2018
ms.keywords: NtCreateKey, ZwCreateKey, ZwCreateKey routine [Kernel-Mode Driver Architecture], k111_1ab9fba3-0c39-45b8-9a79-d33ad73c0642.xml, kernel.zwcreatekey, wdm/NtCreateKey, wdm/ZwCreateKey
f1_keywords:
 - "wdm/ZwCreateKey"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwCreateKey
- NtCreateKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwCreateKey function


## -description


The <b>ZwCreateKey</b> routine creates a new registry key or opens an existing one.


## -parameters




### -param KeyHandle [out]

Pointer to a HANDLE variable that receives a handle to the key.


### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects (see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>), the caller can specify one or more of the following access rights, which are specific to object directories:

<table>
<tr>
<th><i>DesiredAccess </i>flag</th>
<th>Allows caller to do this</th>
</tr>
<tr>
<td>
KEY_QUERY_VALUE

</td>
<td>
Read key values.

</td>
</tr>
<tr>
<td>
KEY_SET_VALUE

</td>
<td>
Write key values.

</td>
</tr>
<tr>
<td>
KEY_CREATE_SUB_KEY

</td>
<td>
Create subkeys for the key.

</td>
</tr>
<tr>
<td>
KEY_ENUMERATE_SUB_KEYS

</td>
<td>
Read the key's subkeys.

</td>
</tr>
<tr>
<td>
KEY_CREATE_LINK

</td>
<td>
Create a symbolic link to the key. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
KEY_NOTIFY

</td>
<td>
Ask to receive notification when the name, value, or attributes of the key change. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566488">ZwNotifyChangeKey</a>.

</td>
</tr>
</table>
 

The caller can also specify one of the following constants, which combines several ACCESS_MASK flags.

<table>
<tr>
<th>Constant</th>
<th>Consists of these ACCESS_MASK flags</th>
</tr>
<tr>
<td>
KEY_READ

</td>
<td>
STANDARD_RIGHTS_READ, KEY_QUERY_VALUE, KEY_ENUMERATE_SUB_KEYS, and KEY_NOTIFY

</td>
</tr>
<tr>
<td>
KEY_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, KEY_SET_VALUE, and KEY_CREATE_SUBKEY

</td>
</tr>
<tr>
<td>
KEY_EXECUTE

</td>
<td>
Same as KEY_READ.

</td>
</tr>
<tr>
<td>
KEY_ALL_ACCESS

</td>
<td>
STANDARD_RIGHTS_ALL, KEY_QUERY_VALUE, KEY_SET_VALUE, KEY_CREATE_SUB_KEY, KEY_ENUMERATE_SUB_KEYS, KEY_NOTIFY, and KEY_CREATE_LINK

</td>
</tr>
</table>
 


### -param ObjectAttributes [in]

Pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


### -param TitleIndex

Device and intermediate drivers set this parameter to zero. 


### -param Class [in, optional]

Pointer to a Unicode string that contains the key's object class. This information is used by the configuration manager. 


### -param CreateOptions [in]

Specifies the options to apply when creating or opening a key, specified as a compatible combination of the following flags.

<table>
<tr>
<th><i>CreateOptions</i> flag</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_OPTION_VOLATILE

</td>
<td>
Key is not preserved when the system is rebooted.

</td>
</tr>
<tr>
<td>
REG_OPTION_NON_VOLATILE

</td>
<td>
Key is preserved when the system is rebooted.

</td>
</tr>
<tr>
<td>
REG_OPTION_CREATE_LINK

</td>
<td>
The newly created key is a symbolic link. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
REG_OPTION_BACKUP_RESTORE

</td>
<td>
Key should be created or opened with special privileges that allow backup and restore operations. This flag is not used by device and intermediate drivers.

</td>
</tr>
</table>
 


### -param Disposition [out, optional]

Pointer to a variable that receives a value indicating whether a new key was created or an existing one opened.

<table>
<tr>
<th><i>Disposition</i> value</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_CREATED_NEW_KEY

</td>
<td>
A new key was created.

</td>
</tr>
<tr>
<td>
REG_OPENED_EXISTING_KEY

</td>
<td>
An existing key was opened.

</td>
</tr>
</table>
 


## -returns



<b>ZwCreateKey</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.




## -remarks



<b>ZwCreateKey</b> supplies a handle that the caller can use to manipulate a registry key. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-the-registry-in-a-driver">Using the Registry in a Driver</a>.

Once the handle pointed to by <i>KeyHandle</i> is no longer in use, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> to close it.

There are two alternate ways to specify the name of the file to be created or opened with <b>ZwCreateKey</b>:

<ol>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes</i>. The pathnames of registry keys begin with <b>\Registry</b>.

</li>
<li>
As pathname relative to another registry key, represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i>. 

</li>
</ol>
If the key specified by <i>ObjectAttributes</i> does not exist, the routine attempts to create the key. For this attempt to succeed, the new key must be a direct subkey of the key that is referred to by <b>RootDirectory</b>, and the key that <b>RootDirectory</b> refers to must have been opened for KEY_CREATE_SUB_KEY access.

If the specified key already exists, it is opened and its value is not affected in any way.

The security attributes specified by <i>ObjectAttributes</i> when a key is created determine whether the specified <i>DesiredAccess</i> is granted on subsequent calls to <b>ZwCreateKey</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-handles">Object Handles</a>.

For more information about working with registry keys, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-the-registry-in-a-driver">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtCreateKey</b>" instead of "<b>ZwCreateKey</b>".</div>
<div> </div>
The <b>NtCreateKey</b> routine in the Windows kernel is not directly accessible to kernel-mode drivers. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwdeletekey">ZwDeleteKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratekey">ZwEnumerateKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwflushkey">ZwFlushKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566488">ZwNotifyChangeKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey">ZwQueryValueKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>
 

 

