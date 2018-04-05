---
UID: NS:wdm._OB_CALLBACK_REGISTRATION
title: "_OB_CALLBACK_REGISTRATION"
author: windows-driver-content
description: The OB_CALLBACK_REGISTRATION structure specifies the parameters when the ObRegisterCallbacks routine registers ObjectPreCallback and ObjectPostCallback callback routines.
old-location: kernel\ob_callback_registration.htm
old-project: kernel
ms.assetid: e288b050-0875-4c9b-aa72-47845861755a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*POB_CALLBACK_REGISTRATION, OB_CALLBACK_REGISTRATION, OB_CALLBACK_REGISTRATION structure [Kernel-Mode Driver Architecture], POB_CALLBACK_REGISTRATION, POB_CALLBACK_REGISTRATION structure pointer [Kernel-Mode Driver Architecture], _OB_CALLBACK_REGISTRATION, kernel.ob_callback_registration, kstruct_c_8357a6f5-881d-4840-a530-454383ba3ddd.xml, wdm/OB_CALLBACK_REGISTRATION, wdm/POB_CALLBACK_REGISTRATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2008.
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
-	OB_CALLBACK_REGISTRATION
product:
- Windows
targetos: Windows
req.typenames: OB_CALLBACK_REGISTRATION, *POB_CALLBACK_REGISTRATION
req.product: Windows 10 or later.
---

# _OB_CALLBACK_REGISTRATION structure


## -description


The <b>OB_CALLBACK_REGISTRATION</b> structure specifies the parameters when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558692">ObRegisterCallbacks</a> routine registers <a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff557741">ObjectPostCallback</a> callback routines.


## -struct-fields




### -field Version

The version of object callback registration that is requested. Drivers should specify OB_FLT_REGISTRATION_VERSION.


### -field OperationRegistrationCount

The number of entries in the <b>OperationRegistration</b> array.


### -field Altitude

A Unicode string that specifies the altitude of the driver. For more information about altitude, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/load-order-groups-and-altitudes-for-minifilter-drivers">Load Order Groups and Altitudes for Minifilter Drivers</a>.


### -field RegistrationContext

The system passes the <b>RegistrationContext</b> value to the callback routine when the callback routine is run. The meaning of this value is driver-defined.


### -field OperationRegistration

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff558718">OB_OPERATION_REGISTRATION</a> structures. Each structure specifies <a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff557741">ObjectPostCallback</a> callback routines and the types of operations that the routines are called for. 


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558692">ObRegisterCallbacks</a> routine. The <i>CallBackRegistration</i> parameter to this routine is a pointer to a buffer that contains an <b>OB_CALLBACK_REGISTRATION</b> structure that is followed by an array of one or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff558718">OB_OPERATION_REGISTRATION</a> structures.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558718">OB_OPERATION_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558692">ObRegisterCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557741">ObjectPostCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a>
 

 

