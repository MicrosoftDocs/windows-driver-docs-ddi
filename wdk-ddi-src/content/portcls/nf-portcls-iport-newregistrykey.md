---
UID: NF:portcls.IPort.NewRegistryKey
title: IPort::NewRegistryKey (portcls.h)
description: The NewRegistryKey method either opens an existing registry key or creates a new key in the registry. The method creates a registry-key object to represent the key. 
tech.root: audio
ms.assetid: 012f6963-9091-4b76-88c6-040e4f5217c1
ms.date: 10/31/2018
ms.topic: method
f1_keywords:
 - "portcls/IPort.NewRegistryKey"
ms.keywords: IPort::NewRegistryKey, NewRegistryKey, IPort.NewRegistryKey, IPort::NewRegistryKey, IPort.NewRegistryKey
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
 - COM
api_location: 
 - portcls.h
api_name: 
 - IPort.NewRegistryKey
product: 
 - Windows
targetos: Windows

---

# IPort::NewRegistryKey


## -description

The NewRegistryKey method either opens an existing registry key or creates a new key in the registry. The method creates a registry-key object to represent the key and outputs a reference to this object to the caller. The caller then accesses the key through the object's IRegistryKey interface.

## -parameters

### -param OutRegistryKey
Pointer to a caller-allocated pointer variable into which the method writes the reference to the IRegistryKey object. This object represents the registry key that is being opened or created. The caller must specify a valid, non-NULL pointer value for this parameter.

### -param OuterUnknown
Pointer to the IUnknown interface of an object that needs to aggregate the registry key object. This parameter is optional. If aggregation is not required, specify this parameter as NULL.

### -param RegistryKeyType
Specifies the type of registry key that the caller is requesting access to. For more information, see the following Remarks section.


### -param DesiredAccess
An access-control mask that specifies the type of access that the caller requires to the key. This parameter is of type ACCESS_MASK. For more information, see the following Remarks section.

### -param ObjectAttributes
Pointer to the object attributes of the key being created or opened. If RegistryKeyType has the value GeneralRegistryKey, this parameter must point to a valid, initialized system structure of type OBJECT_ATTRIBUTES with a valid ObjectName string for the key; otherwise, the method does not use this parameter. For more information, see the following Remarks section.

### -param CreateOptions
Flags indicating the create options. Can be zero if none are desired. This parameter is required if RegistryKeyType has the value GeneralRegistryKey; otherwise, the method does not use this parameter. For more information, see the following Remarks section.


### -param Disposition
Pointer to a caller-allocated ULONG variable into which the method writes a status value indicating whether a new key was created or an existing key was opened. This parameter is optional and can be specified as NULL if the caller does not need the status value. The method uses this parameter only if RegistryKeyType has the value GeneralRegistryKey. The method does not use the parameter for any of the other key types. For more information, see the following Remarks section.


## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks

The DesiredAccess, ObjectAttributes, and Disposition parameters take on the values that are defined for the parameters with the same names in the ZwCreateKey call.

If the RegistryKeyType parameter has the value GeneralRegistryKey, then the NewRegistryKey method either opens an existing registry key or creates a new key in the registry, as indicated by the value that the method outputs through the Disposition parameter. If the key type is any value other than GeneralRegistryKey, then the method opens an already existing key that was previously created during Plug and Play device enumeration.

The caller should set the RegistryKeyType parameter to one of the enumeration values shown in the following table.

RegistryKeyType Value | Meaning 
----------------------|-----------
GeneralRegistryKey | Provide generic access to any key type. Opens the key if it exists or creates the key if it does not.
 DeviceRegistryKey | Open an existing key containing device-specific information.
 DriverRegistryKey |  Open an existing key containing driver-specific information.
 HwProfileRegistryKey | Open an existing key relative to the current hardware profile for device or driver information. This allows the driver to access configuration information that is hardware-profile-specific.
DeviceInterfaceRegistryKey | Open an existing registry key containing information about a particular device-interface instance.
 
For a RegistryKeyType value of GeneralRegistryKey, the caller must provide a valid ObjectAttributes parameter value, and the CreateOptions and Disposition parameters are optional. For any other RegistryKeyType value, the caller must provide a valid DeviceObject parameter value, and the CreateOptions and Disposition parameters are not used.

The ObjectAttributes parameter points to an opaque structure of type OBJECT_ATTRIBUTES that contains object attributes such as key name and security descriptor. Use the InitializeObjectAttributes macro to initialize the structure. In the Attributes parameter for this macro, set the OBJ_KERNEL_HANDLE flag unless you intend to allow non-secure, user-mode applications to have read/write access to the registry key.

The DesiredAccess parameter is an access-control mask. It specifies the type of access control that the caller needs to have to the new registry key when accessing it through the OutRegistryKey object. This mask should not be confused with the ACL (access control list) that controls access by users to the registry key. When calling NewRegistryKey to create a registry key of type GeneralRegistryKey, the ObjectAttributes parameter specifies the key's attributes, including a security descriptor that contains the ACL. However, if the key type is GeneralRegistryKey and either the security descriptor pointer in the ObjectAttributes structure is NULL or the ACL pointer in the security descriptor is NULL, then the new key created by the call will inherit the parent key's ACL by default.

If the key is not of type GeneralRegistryKey, then the key retains the ACL that Plug and Play assigned to the key when it was created during device enumeration.

The NewRegistryKey method is similar to the PcNewRegistryKey function except that the device object and port object must be explicitly specified in a PcNewRegistryKey call but are simply implied in a NewRegistryKey call. PcNewRegistryKey is typically called by adapter drivers. Miniport drivers typically call NewRegistryKey instead.

Once a registry key has been created or opened by a call to either NewRegistryKey or PcNewRegistryKey, the IRegistryKey::NewSubKey method can be used to create subkeys under that key.

The OutRegistryKey and OuterUnknown parameters follow the reference-counting conventions for COM objects.



## -see-also

[IPort](nn-portcls-iport.md)
