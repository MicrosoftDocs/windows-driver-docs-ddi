---
UID: NS:wdm._REG_UNLOAD_KEY_INFORMATION
title: "_REG_UNLOAD_KEY_INFORMATION"
author: windows-driver-content
description: The REG_UNLOAD_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry hive is unloaded.
old-location: kernel\reg_unload_key_information.htm
old-project: kernel
ms.assetid: 171d712d-89e0-44f4-aa52-b9048c20abf2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PREG_UNLOAD_KEY_INFORMATION, PREG_UNLOAD_KEY_INFORMATION, PREG_UNLOAD_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_UNLOAD_KEY_INFORMATION, REG_UNLOAD_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_UNLOAD_KEY_INFORMATION, kernel.reg_unload_key_information, kstruct_d_3a289907-a70f-4245-a54c-5df9a71da3e6.xml, wdm/PREG_UNLOAD_KEY_INFORMATION, wdm/REG_UNLOAD_KEY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	REG_UNLOAD_KEY_INFORMATION
product: Windows
targetos: Windows
req.typenames: REG_UNLOAD_KEY_INFORMATION, *PREG_UNLOAD_KEY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_UNLOAD_KEY_INFORMATION structure


## -description


The <b>REG_UNLOAD_KEY_INFORMATION</b> structure contains information that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can use when a registry hive is unloaded.


## -struct-fields




### -field Object

A pointer to a registry key object. This object represents the root key of the hive that is being unloaded.


### -field UserEvent

A pointer to an event object.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined starting with Windows Vista.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.


### -field Reserved

This member is reserved for future use. This member is defined starting with Windows Vista.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine. When the <i>Argument1</i> parameter to the <i>RegistryCallback</i> routine is <b>RegNtPreUnloadKey</b>, the <i>Argument2</i> parameter is a pointer to a <b>REG_UNLOAD_KEY_INFORMATION</b> structure.

The operating system passes the <b>REG_UNLOAD_KEY_INFORMATION</b> structure to the <i>RegistryCallback</i> routine every time a thread attempts to unload a key—for example, when a user-mode thread calls the <a href="https://msdn.microsoft.com/73b4b6a9-4acb-4247-bd7f-82024ba3e14a">RegUnloadKey</a> function. In response to a <b>RegNtPreUnloadKey</b> notification, the <i>RegistryCallback</i> routine should free any resources the driver previously allocated for use with the hive before the hive is unloaded.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
 

 

