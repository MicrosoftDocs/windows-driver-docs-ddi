---
UID: NF:portcls.PcNewRegistryKey
title: PcNewRegistryKey function
author: windows-driver-content
description: The PcNewRegistryKey function opens or creates a new registry key and creates an IRegistryKey object to represent the key. The caller accesses the key through this object.
old-location: audio\pcnewregistrykey.htm
tech.root: audio
ms.assetid: d8ef9e7f-8ce0-48df-973f-170c47e55777
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: PcNewRegistryKey, PcNewRegistryKey function [Audio Devices], audio.pcnewregistrykey, audpc-routines_67ac1fc2-b40b-4176-8a86-0f4d6eb15e6a.xml, portcls/PcNewRegistryKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewRegistryKey function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcNewRegistryKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcNewRegistryKey function


## -description


The <b>PcNewRegistryKey</b> function opens or creates a new registry key and creates an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536965">IRegistryKey</a> object to represent the key. The caller accesses the key through this object.


## -parameters




### -param OutRegistryKey [out]

Output pointer to the registry-key object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536965">IRegistryKey</a> object. The object represents the registry key being opened or created. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the <i>OutRegistryKey</i> object. Unless aggregation is required, set this parameter to <b>NULL</b>.


### -param RegistryKeyType [in]

Specifies the type of registry key that the caller wants to create or open. For more information, see the following Remarks section.


### -param DesiredAccess [in]

Specifies an access-control mask. This parameter is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>. It indicates the type of access that the caller is requesting to the registry key that is to be opened or created. For more information, see the following Remarks section.


### -param DeviceObject [in, optional]

Pointer to the adapter driver's device object. This pointer is cast to type PVOID. If <i>RegistryKeyType</i> is any value other than <b>GeneralRegistryKey</b>, this parameter must point to a valid, initialized system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>. If the value of <i>RegistryKeyType</i> is <b>GeneralRegistryKey</b>, the <b>PcNewRegistryKey</b> function does not use this parameter. For more information, see the following Remarks section.


### -param SubDevice [in, optional]

Specifies the aspect of the device that is to be offered to clients. Adapter drivers must assign the value <b>NULL</b> to this parameter.


### -param ObjectAttributes [in, optional]

Pointer to the object attributes of the key being created or opened. If <i>RegistryKeyType</i> has the value <b>GeneralRegistryKey</b>, this parameter must point to a valid, initialized system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> with a valid <i>ObjectName</i> string for the key; otherwise, the function does not use this parameter. For more information, see the following Remarks section.


### -param CreateOptions [in, optional]

Specifies the create options. Can be zero if none are desired. If <i>RegistryKeyType</i> is not <b>GeneralRegistryKey</b>, the <b>PcNewRegistryKey</b> function ignores this parameter. For more information, see the following Remarks section.


### -param Disposition [out, optional]

Pointer to a variable that receives a value indicating whether a key was created or an existing key was opened. This parameter is optional and can be specified as <b>NULL</b>. If <i>RegistryKeyType</i> is any value other than <b>GeneralRegistryKey</b>, the <b>PcNewRegistryKey</b> function ignores this parameter. For more information, see the following Remarks section.


## -returns



<b>PcNewRegistryKey</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



If the <i>RegistryKeyType</i> parameter's value is <b>GeneralRegistryKey</b>, then the <b>PcNewRegistryKey</b> function either opens an existing key or creates a new key in the registry, as indicated by the value that the function outputs through the <i>Disposition</i> parameter. If the key is of any type other than <b>GeneralRegistryKey</b>, then the function opens an already existing key that was previously created during Plug and Play device enumeration.

The <i>DesiredAccess</i>, <i>ObjectAttributes</i>, <i>CreateOptions</i>, and <i>Disposition</i> parameters take on the values that are defined for the parameters with the same names in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> call.

The <i>RegistryKeyType</i> parameter should be set to one of the enumeration values shown in the following table.

<table>
<tr>
<th>RegistryKeyType value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>GeneralRegistryKey</b>

</td>
<td>
Provide generic access to any key type. Open the specified key if it already exists or create the key if it does not.

</td>
</tr>
<tr>
<td>
<b>DeviceRegistryKey</b>

</td>
<td>
Open an existing key containing device-specific information. The key is located under the key for the device instance specified by <i>DeviceObject</i>.

</td>
</tr>
<tr>
<td>
<b>DriverRegistryKey</b>

</td>
<td>
Open an existing key containing driver-specific information.

</td>
</tr>
<tr>
<td>
<b>HwProfileRegistryKey</b>

</td>
<td>
Open an existing key relative to the current hardware profile containing device or driver information. This allows the driver to access configuration information that is hardware-profile-specific.

</td>
</tr>
<tr>
<td>
<b>DeviceInterfaceRegistryKey</b>

</td>
<td>
Not used with <b>PcNewRegistryKey</b>. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a> for details.

</td>
</tr>
</table>
 

For a <i>RegistryKeyType</i> value of <b>GeneralRegistryKey</b>, the caller must provide a valid <i>ObjectAttributes</i> parameter value, and the <i>CreateOptions</i> and <i>Disposition</i> parameters are optional. For any other <i>RegistryKeyType</i> value, the caller must provide a valid <i>DeviceObject</i> parameter value, and the <i>CreateOptions</i> and <i>Disposition</i> parameters are not used.

The <i>ObjectAttributes</i> parameter points to an opaque structure of type OBJECT_ATTRIBUTES that contains object attributes such as key name and security descriptor. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> macro to initialize the structure. In the <i>Attributes</i> parameter for this macro, set the OBJ_KERNEL_HANDLE flag unless you intend to allow non-secure, user-mode applications to have read/write access to the registry key.

The <i>DesiredAccess</i> parameter is an access-control mask. It specifies the type of access control that the caller needs to have to the new registry key when accessing it through the <i>OutRegistryKey</i> object. This mask should not be confused with the access control list (ACL) that controls access by users to the registry key. When calling <b>PcNewRegistryKey</b> to create a registry key of type <b>GeneralRegistryKey</b>, the <i>ObjectAttributes </i>parameter specifies the key's attributes, including a security descriptor that contains the ACL. However, if the new key is of type <b>GeneralRegistryKey</b> and either the security descriptor pointer in the <i>ObjectAttributes </i>structure is <b>NULL</b> or the ACL pointer in the security descriptor is <b>NULL</b>, then the new key will inherit the parent key's ACL by default.

If the key is of any type other than <b>GeneralRegistryKey</b>, then the key retains the ACL that Plug and Play assigned to the key when it was created during device enumeration.

The <b>PcNewRegistryKey</b> function is similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a> method except that the device object and port object must be explicitly specified in a <b>PcNewRegistryKey</b> call but are simply implied in a <b>NewRegistryKey</b> call. <b>PcNewRegistryKey</b> is used primarily by adapter drivers. Miniport drivers typically call <b>NewRegistryKey</b> instead.

The <i>OutRegistryKey</i> and <i>OuterUnknown</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536965">IRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>
 

 

