---
UID: NF:wdm.ZwOpenKeyEx
title: ZwOpenKeyEx function (wdm.h)
description: The ZwOpenKeyEx routine opens an existing registry key.
old-location: kernel\zwopenkeyex.htm
tech.root: kernel
ms.assetid: 05057ae7-0f91-4f5a-8c72-652ec04ee3ab
ms.date: 04/30/2018
ms.keywords: ZwOpenKeyEx, ZwOpenKeyEx routine [Kernel-Mode Driver Architecture], k111_4e01a648-6ffc-418f-821c-9a4ef821dc3b.xml, kernel.zwopenkeyex, wdm/ZwOpenKeyEx
ms.topic: function
f1_keywords:
 - "wdm/ZwOpenKeyEx"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwOpenKeyEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwOpenKeyEx function


## -description


The <b>ZwOpenKeyEx</b> routine opens an existing registry key. 


## -parameters




### -param KeyHandle [out]

A pointer to a HANDLE variable into which the routine writes the handle to the key.


### -param DesiredAccess [in]

Specifies the type of access to the key that the caller requests. This parameter is an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value. For more information, see the description of the <i>DesiredAccess</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> routine.


### -param ObjectAttributes [in]

A pointer to the object attributes of the key being opened. This parameter points to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that must have been previously initialized by the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine. The caller must specify the name of the registry key as the <i>ObjectName</i> parameter in the call to <b>InitializeObjectAttributes</b>. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


### -param OpenOptions [in]

Specifies the options to apply when opening the key. Set this parameter to zero or to the bitwise OR of one or more of the following REG_OPTION_<i>XXX</i> flag bits:

<table>
<tr>
<th><i>OpenOptions</i> flag</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_OPTION_OPEN_LINK

</td>
<td>
The key is a symbolic link. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
REG_OPTION_BACKUP_RESTORE

</td>
<td>
The key should be opened with special privileges that allow backup and restore operations. This flag is not used by device and intermediate drivers.

</td>
</tr>
</table>
 


## -returns



<b>ZwOpenKeyEx</b> returns STATUS_SUCCESS if the call succeeds in opening the key. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The <i>OpenOptions</i> parameter specifies invalid options. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The registry path in the object attributes is invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry key name in the object attributes was not found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The named registry key is a symbolic link, but the REG_OPTION_OPEN_LINK flag bit is not set in <i>OpenOptions</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required access rights to open a handle for the named registry key.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory allocation operation failed. 

</td>
</tr>
</table>
 




## -remarks



This routine supplies a handle with which the caller can access a registry key. If the specified key does not exist, the routine returns an error status value and does not supply a key handle.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwopenkey">ZwOpenKey</a> routine is similar to <b>ZwOpenKeyEx</b> but does not accept an <i>OpenOptions</i> parameter. The <i>OpenOptions</i> parameter of <b>ZwOpenKeyEx</b> enables the caller to open a key that is a symbolic link, or to open a key for backup and restore operations. A call to <b>ZwOpenKeyEx</b> with <i>OpenOptions</i> = 0 is equivalent to a call to <b>ZwOpenKey</b>.

After the handle pointed to by <i>KeyHandle</i> is no longer in use, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntclose">ZwClose</a> to close it.

<b>ZwOpenKeyEx</b> ignores the security information in the structure that the <i>ObjectAttributes</i> parameter points to.

If the kernel-mode caller is not running in a system thread context, it must ensure that any handles it creates are kernel handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-handles">Object Handles</a>.

For more information about working with registry keys in kernel mode, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-the-registry-in-a-driver">Using the Registry in a Driver</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>
 

 

