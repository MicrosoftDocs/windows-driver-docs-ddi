---
UID: NS:wdm._REG_ENUMERATE_KEY_INFORMATION
title: _REG_ENUMERATE_KEY_INFORMATION (wdm.h)
description: The REG_ENUMERATE_KEY_INFORMATION structure describes one subkey of a key whose subkeys are being enumerated.
old-location: kernel\reg_enumerate_key_information.htm
tech.root: kernel
ms.assetid: fdae9130-b33e-4714-9e8c-f4faf21ee8c8
ms.date: 04/30/2018
ms.keywords: "*PREG_ENUMERATE_KEY_INFORMATION, PREG_ENUMERATE_KEY_INFORMATION, PREG_ENUMERATE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_ENUMERATE_KEY_INFORMATION, REG_ENUMERATE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_ENUMERATE_KEY_INFORMATION, kernel.reg_enumerate_key_information, kstruct_d_e20923be-cb64-43a0-b3d0-a28290fadc07.xml, wdm/PREG_ENUMERATE_KEY_INFORMATION, wdm/REG_ENUMERATE_KEY_INFORMATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- REG_ENUMERATE_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_ENUMERATE_KEY_INFORMATION, *PREG_ENUMERATE_KEY_INFORMATION
---

# _REG_ENUMERATE_KEY_INFORMATION structure


## -description


The <b>REG_ENUMERATE_KEY_INFORMATION</b> structure describes one subkey of a key whose subkeys are being enumerated.


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose subkeys are being enumerated.


### -field Index

The zero-based index of the subkey within the key.


### -field KeyInformationClass

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a> value that indicates the type of information to be returned by the system in the <b>KeyInformation</b> buffer.


### -field KeyInformation

A pointer to a buffer that contains the information to be returned by the system. The format of the buffer depends on the value of <b>KeyInformationClass</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>.


### -field Length

The size, in bytes, of the <b>KeyInformation</b> buffer.


### -field ResultLength

A pointer to a ULONG that receives (from the system) the amount of valid data, in bytes, in the <b>KeyInformation</b> buffer. 


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



The system passes this structure to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to enumerate the subkeys of a key—for example, when a user-mode thread calls <b>RegEnumKey</b> or <b>RegEnumKeyEx</b> or when a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>
 

 

