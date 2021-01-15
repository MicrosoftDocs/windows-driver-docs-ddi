---
UID: NS:wdm._REG_CREATE_KEY_INFORMATION_V1
title: _REG_CREATE_KEY_INFORMATION_V1 (wdm.h)
description: The REG_CREATE_KEY_INFORMATION_V1 structure contains information that a filter driver's RegistryCallback routine can use when a registry key is being created.
old-location: kernel\reg_create_key_information_v1.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["REG_CREATE_KEY_INFORMATION_V1 structure"]
ms.keywords: "*PREG_CREATE_KEY_INFORMATION_V1, *PREG_OPEN_KEY_INFORMATION_V1, PREG_CREATE_KEY_INFORMATION_V1, PREG_CREATE_KEY_INFORMATION_V1 structure pointer [Kernel-Mode Driver Architecture], PREG_OPEN_KEY_INFORMATION_V1, PREG_OPEN_KEY_INFORMATION_V1 structure pointer [Kernel-Mode Driver Architecture], REG_CREATE_KEY_INFORMATION_V1, REG_CREATE_KEY_INFORMATION_V1 structure [Kernel-Mode Driver Architecture], REG_OPEN_KEY_INFORMATION_V1, REG_OPEN_KEY_INFORMATION_V1 structure [Kernel-Mode Driver Architecture], _REG_CREATE_KEY_INFORMATION_V1, kernel.reg_create_key_information_v1, kstruct_d_79809cef-3593-4774-8407-c26c281735eb.xml, wdm/PREG_CREATE_KEY_INFORMATION_V1, wdm/PREG_OPEN_KEY_INFORMATION_V1, wdm/REG_CREATE_KEY_INFORMATION_V1, wdm/REG_OPEN_KEY_INFORMATION_V1"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows 7 and later versions of the Windows operating systems.
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
req.irql: 
targetos: Windows
req.typenames: REG_CREATE_KEY_INFORMATION_V1, REG_OPEN_KEY_INFORMATION_V1, *PREG_CREATE_KEY_INFORMATION_V1, *PREG_OPEN_KEY_INFORMATION_V1
f1_keywords:
 - _REG_CREATE_KEY_INFORMATION_V1
 - wdm/_REG_CREATE_KEY_INFORMATION_V1
 - PREG_CREATE_KEY_INFORMATION_V1
 - wdm/PREG_CREATE_KEY_INFORMATION_V1
 - REG_CREATE_KEY_INFORMATION_V1
 - wdm/REG_CREATE_KEY_INFORMATION_V1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _REG_CREATE_KEY_INFORMATION_V1
 - PREG_CREATE_KEY_INFORMATION_V1
 - REG_CREATE_KEY_INFORMATION_V1
---

# _REG_CREATE_KEY_INFORMATION_V1 structure


## -description

The <b>REG_CREATE_KEY_INFORMATION_V1</b> structure contains information that a filter driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can use when a registry key is being created.

## -struct-fields

### -field CompleteName

A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the path of the new registry key. The path can be absolute or relative. If the path is absolute, this structure contains a fully qualified path that starts with the "\\" character. For an absolute path, the <b>RootObject</b> member specifies the <b>\REGISTRY</b> key, which is the root directory of the registry tree. If the path is relative, the path starts with a character other than "\\", and is relative to the key that is specified by the <b>RootObject</b> member.

### -field RootObject

A pointer to a registry key object that represents the root registry key for the path that is specified by the <b>CompleteName</b> member.

### -field ObjectType

This member is reserved for use by the operating system. Drivers must not access this member.

### -field Options

Specifies the options for the key-create routine to use to create or open the new key. For more information, see the description of the <i>CreateOptions</i> parameter of the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> routine and the description of the <i>OpenOptions</i> parameter of the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkeyex">ZwOpenKeyEx</a> routine.

### -field Class

A pointer to a <b>UNICODE_STRING</b> structure that identifies the object class of the new key. For more information about this member, see the <i>Class</i> parameter of the <b>ZwCreateKey</b> routine. This pointer value can be <b>NULL</b>.

### -field SecurityDescriptor

A pointer to a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure that contains security information for the key object. This pointer was obtained from the <b>SecurityDescriptor</b> member of the <a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that was passed as an input parameter in the call to create the new registry key.

### -field SecurityQualityOfService

A pointer to a <a href="/windows/win32/api/winnt/ns-winnt-security_quality_of_service">SECURITY_QUALITY_OF_SERVICE</a> structure. This structure indicates whether a server can impersonate the client that is trying to create the registry key, and, if impersonation is permitted, the extent to which it is permitted.

### -field DesiredAccess

The access mask that was specified by the thread that is trying to create the registry key. For more information about this access mask, see the description of the <i>DesiredAccess</i> parameter of the <b>ZwCreateKey</b> routine.

### -field GrantedAccess

An access mask that indicates the access rights that were granted to the thread that is trying to create the registry key. For more information about this member, see the following Remarks section.

### -field Disposition

A value that indicates whether the requested registry operation will create a new key or open an existing one. For more information about this member, see the description of the <i>Disposition</i> parameter of the <b>ZwCreateKey</b> routine and the following Remarks section.

### -field ResultObject

A pointer to a location that receives the address of the key object that represents the created registry key.

### -field CallContext

Optional driver-defined context information that the driver's <i>RegistryCallback</i> routine can supply.

### -field RootObjectContext

A pointer to driver-defined context information that the driver has associated with the root of the path of the registry object by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a> routine.

### -field Transaction

A pointer to a transaction object for the registry operation. You can supply this pointer to the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-obopenobjectbypointer">ObOpenObjectByPointer</a> routine to obtain the corresponding transaction handle. If this member is <b>NULL</b>, the operation is being performed in non-transactional context.

### -field Version

The structure version number. This member distinguishes the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information">REG_CREATE_KEY_INFORMATION</a> structure in Windows Vista from the <b>REG_CREATE_KEY_INFORMATION_V1</b> structure in Windows 7 and later versions of Windows. The following version numbers are currently defined.

<table>
<tr>
<th>Version number</th>
<th>Version of structure</th>
</tr>
<tr>
<td>
0

</td>
<td>
<b>REG_CREATE_KEY_INFORMATION</b>

</td>
</tr>
<tr>
<td>
1

</td>
<td>
<b>REG_CREATE_KEY_INFORMATION_V1</b>

</td>
</tr>
</table>
 

Future versions of this structure might add new members but will not change the members that are already defined in existing versions of the structure. This member is defined in the <b>REG_CREATE_KEY_INFORMATION_V1</b> structure that is supported in Windows 7 and later versions of the Windows operating systems. In the <b>REG_CREATE_KEY_INFORMATION</b> structure that Windows Vista supports, this member is named <b>Reserved</b> and is set to zero. Filter drivers should rely on the version number and not the operating system version to determine which version of the structure they are using.

### -field RemainingName

A pointer to a <b>UNICODE_STRING</b> structure that contains the relative path of the new registry key. This member always expresses the path of the new key relative to the path of the key that is specified by the <b>RootObject</b> member. In contrast, the <b>CompleteName</b> member can contain an absolute path if the <b>RootObject</b> member specifies the <b>\REGISTRY</b> key.

### -field Wow64Flags

Contains the Wow64 flags from the access mask that was passed as an input parameter in the call to create the new registry key. This member indicates whether a 32-bit client program that is running on a 64-bit version of Windows is trying to create a registry key. This member is set to zero or to one of the following flag bits:

<ul>
<li>
KEY_WOW64_32KEY

</li>
<li>
KEY_WOW64_64KEY

</li>
</ul>
These flag bits are defined in the Wdm.h and Winnt.h header files. For more information about these flags, see <a href="/windows/win32/sysinfo/registry-key-security-and-access-rights">Registry Key Security and Access Rights</a>.

### -field Attributes

Contains the object-attribute flags from the <b>Attributes</b> member of the <b>OBJECT_ATTRIBUTES</b> structure that was passed as an input parameter in the call to create the new registry key. This member might contain one or more of the following flag bits:

<ul>
<li>
OBJ_KERNEL_HANDLE

</li>
<li>
OBJ_FORCE_ACCESS_CHECK

</li>
<li>
OBJ_OPENLINK

</li>
</ul>
For more information about these flags, see <a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>.

### -field CheckAccessMode

Indicates how the configuration manager performs the security access check for the call to create the new key. This member contains one of the following MODE enumeration values from the Wdm.h header file:

<ul>
<li>
<b>KernelMode</b>

</li>
<li>
<b>UserMode</b>

</li>
</ul>
This security check is similar to that performed by the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-seaccesscheck">SeAccessCheck</a> routine, which has an <i>AccessMode</i> parameter that can be set to either <b>UserMode</b> or <b>KernelMode</b>. If <b>CheckAccessMode</b> is set to <b>UserMode</b>, the configuration manager performs a full security access check regardless of whether the call originated in user mode or kernel mode. For more information about how to force user-mode security access checks on a call that originates in kernel mode, see the description of the OBJ_FORCE_ACCESS_CHECK flag in the <b>Attributes</b> member of the <b>OBJECT_ATTRIBUTES</b> structure.

## -remarks

The configuration manager passes this structure to the <i>RegistryCallback</i> routine every time that a thread tries to create a key—for example, when a user-mode thread calls <a href="/windows/win32/api/winreg/nf-winreg-regcreatekeya">RegCreateKey</a> or <a href="/windows/win32/api/winreg/nf-winreg-regcreatekeyexa">RegCreateKeyEx</a>, or when a kernel-mode driver calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>.

This structure is an extended version of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information">REG_CREATE_KEY_INFORMATION</a> structure that Windows Vista supports. The first 14 members, <b>CompleteName</b> through <b>Transaction</b>, are identical in the two structures. The last five members of the <b>REG_CREATE_KEY_INFORMATION_V1</b> structure, <b>Version</b> through <b>CheckAccessMode</b>, are not part of the <b>REG_CREATE_KEY_INFORMATION</b> structure.

If the driver's <i>RegistryCallback</i> routine returns STATUS_CALLBACK_BYPASS for a <b>RegNtPreCreateKeyEx</b> notification, the driver must supply the values for the <b>GrantedAccess</b>, <b>Disposition</b>, and <b>ResultObject</b> members. 

The <b>REG_CREATE_KEY_INFORMATION_V1</b> structure is one of a number of structures that a filter driver can receive through its <i>RegistryCallback</i> routine. For more information about registry filtering operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-obopenobjectbypointer">ObOpenObjectByPointer</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information">REG_CREATE_KEY_INFORMATION</a>



<a href="/windows/win32/api/winreg/nf-winreg-regcreatekeya">RegCreateKey</a>



<a href="/windows/win32/api/winreg/nf-winreg-regcreatekeyexa">RegCreateKeyEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="/windows/win32/api/winnt/ns-winnt-security_quality_of_service">SECURITY_QUALITY_OF_SERVICE</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>

