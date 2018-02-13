---
UID: NS:wdm._OB_CALLBACK_REGISTRATION
title: "_OB_CALLBACK_REGISTRATION"
author: windows-driver-content
description: The OB_CALLBACK_REGISTRATION structure specifies the parameters when the ObRegisterCallbacks routine registers ObjectPreCallback and ObjectPostCallback callback routines.
old-location: kernel\ob_callback_registration.htm
old-project: kernel
ms.assetid: e288b050-0875-4c9b-aa72-47845861755a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.ob_callback_registration, POB_CALLBACK_REGISTRATION structure pointer [Kernel-Mode Driver Architecture], wdm/OB_CALLBACK_REGISTRATION, kstruct_c_8357a6f5-881d-4840-a530-454383ba3ddd.xml, POB_CALLBACK_REGISTRATION, wdm/POB_CALLBACK_REGISTRATION, OB_CALLBACK_REGISTRATION, _OB_CALLBACK_REGISTRATION, OB_CALLBACK_REGISTRATION structure [Kernel-Mode Driver Architecture], *POB_CALLBACK_REGISTRATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	OB_CALLBACK_REGISTRATION
product: Windows
targetos: Windows
req.typenames: OB_CALLBACK_REGISTRATION, *POB_CALLBACK_REGISTRATION
req.product: Windows 10 or later.
---

# _OB_CALLBACK_REGISTRATION structure


## -description


The <b>OB_CALLBACK_REGISTRATION</b> structure specifies the parameters when the <a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a> routine registers <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> and <a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a> callback routines.


## -syntax


````
typedef struct _OB_CALLBACK_REGISTRATION {
  USHORT                    Version;
  USHORT                    OperationRegistrationCount;
  UNICODE_STRING            Altitude;
  PVOID                     RegistrationContext;
  OB_OPERATION_REGISTRATION *OperationRegistration;
} OB_CALLBACK_REGISTRATION, *POB_CALLBACK_REGISTRATION;
````


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

A pointer to an array of <a href="..\wdm\ns-wdm-_ob_operation_registration.md">OB_OPERATION_REGISTRATION</a> structures. Each structure specifies <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> and <a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a> callback routines and the types of operations that the routines are called for. 


## -remarks



This structure is used by the <a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a> routine. The <i>CallBackRegistration</i> parameter to this routine is a pointer to a buffer that contains an <b>OB_CALLBACK_REGISTRATION</b> structure that is followed by an array of one or more <a href="..\wdm\ns-wdm-_ob_operation_registration.md">OB_OPERATION_REGISTRATION</a> structures.




## -see-also

<a href="..\wdm\ns-wdm-_ob_operation_registration.md">OB_OPERATION_REGISTRATION</a>



<a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a>



<a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a>



<a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_CALLBACK_REGISTRATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

