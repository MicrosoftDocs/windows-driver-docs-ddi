---
UID: NF:portcls.IRegistryKey.NewSubKey
title: IRegistryKey::NewSubKey
author: windows-driver-content
description: The NewSubKey method either creates a new registry subkey or opens an existing subkey under the key represented by the IRegistryKey object.
old-location: audio\iregistrykey_newsubkey.htm
old-project: audio
ms.assetid: 39b352ba-4b6f-4d9c-baf5-a479d8c74ae0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IRegistryKey interface [Audio Devices],NewSubKey method, IRegistryKey.NewSubKey, IRegistryKey::NewSubKey, NewSubKey, NewSubKey method [Audio Devices], NewSubKey method [Audio Devices],IRegistryKey interface, audio.iregistrykey_newsubkey, audmp-routines_8a9e8a73-551d-46d4-90a8-f24183c38d8d.xml, portcls/IRegistryKey::NewSubKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IRegistryKey.NewSubKey
product: Windows
targetos: Windows
req.typenames: 
---

# IRegistryKey::NewSubKey


## -description


The <code>NewSubKey</code> method either creates a new registry subkey or opens an existing subkey under the key represented by the <b>IRegistryKey</b> object.


## -parameters




### -param RegistrySubKey [out]

Output pointer for the new subkey. This parameter points to a caller-allocated pointer variable into which the method writes the pointer to the new <b>IRegistryKey</b> object. This object represents the subkey being opened or created. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the registry key object. This parameter is optional. If aggregation is not required, specify this parameter as <b>NULL</b>.


### -param DesiredAccess [in]

Specifies the type of access that the caller requires to the subkey that is being opened or created. This parameter is of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>. For more information, see the following Remarks section.


### -param SubKeyName [in]

Pointer to the name that is to be assigned to the subkey. This parameter must be a valid, non-<b>NULL</b> pointer to an initialized structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>.


### -param CreateOptions [in]

Flags indicating the create options. Can be zero if none are desired. This parameter is required if the value of <i>RegistryKeyType</i> is <b>GeneralRegistryKey</b>; otherwise, the method does not use this parameter. For more information, see the following Remarks section.


### -param Disposition [out, optional]

Output pointer for the disposition value. This parameter points to a caller-allocated ULONG variable into which the method writes a status value indicating whether a new key was created or an existing key was opened. This parameter is optional and can be specified as <b>NULL</b> if the caller does not need it. For more information, see the following Remarks section.


## -returns



<code>NewSubKey</code> returns STATUS_SUCCESS if the call was successful in outputting a valid <b>IRegistryKey</b> pointer through the <i>RegistrySubKey</i> parameter. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>NewSubKey</code> method either opens the specified registry key if it already exists, or creates a new key in the registry if it does not exist. The method outputs a pointer to the <b>IRegistryKey</b> interface of the new key through the <i>RegistrySubKey</i> parameter. The method also outputs a status value through the optional <i>Disposition</i> parameter to indicate whether the key was opened or created.

The <i>DesiredAccess</i>, <i>CreateOptions</i>, and <i>Disposition</i> parameters take on the values that are defined for the parameters with the same names in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537716">PcNewRegistryKey</a> call.

The <i>DesiredAccess</i> parameter is an access-control mask that specifies the type of access control that the caller needs to have to the subkey when accessing it through the <i>RegistrySubKey</i> object. This mask should not be confused with the ACL (access control list) that controls access by users to the registry subkey. When the <b>PcNewRegistryKey</b> function or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a> method creates a registry key of type <b>GeneralRegistryKey</b>, the <i>ObjectAttributes</i> parameter specifies the key's attributes, including a security descriptor that contains the ACL. When the <code>NewSubKey</code> method creates a new registry subkey, however, that subkey simply inherits the ACL from its parent key. The <code>NewSubKey</code> method provides no means to specify an ACL that differs from that of the parent key.

The <i>RegistrySubKey</i> and <i>OuterUnknown</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536965">IRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537716">PcNewRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

