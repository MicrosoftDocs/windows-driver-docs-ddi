---
UID: NS:wdm._REG_LOAD_KEY_INFORMATION
title: _REG_LOAD_KEY_INFORMATION (wdm.h)
description: The REG_LOAD_KEY_INFORMATION structure contains information about a registry hive that is being loaded.
old-location: kernel\reg_load_key_information.htm
tech.root: kernel
ms.assetid: 4012667b-d287-4846-8860-0cca977f9792
ms.date: 04/30/2018
keywords: ["_REG_LOAD_KEY_INFORMATION structure"]
ms.keywords: "*PREG_LOAD_KEY_INFORMATION, PREG_LOAD_KEY_INFORMATION, PREG_LOAD_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_LOAD_KEY_INFORMATION, REG_LOAD_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_LOAD_KEY_INFORMATION, kernel.reg_load_key_information, kstruct_d_31dae695-0a6f-4309-9c39-25c2df4a5b23.xml, wdm/PREG_LOAD_KEY_INFORMATION, wdm/REG_LOAD_KEY_INFORMATION"
f1_keywords:
 - "wdm/REG_LOAD_KEY_INFORMATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- REG_LOAD_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_LOAD_KEY_INFORMATION, *PREG_LOAD_KEY_INFORMATION
---

# _REG_LOAD_KEY_INFORMATION structure


## -description


The <b>REG_LOAD_KEY_INFORMATION</b> structure contains information about a registry hive that is being loaded.


## -struct-fields




### -field Object

A pointer to the registry key object for the root key of the hive that is about to be loaded.


### -field KeyName

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the root key.


### -field SourceFile

A pointer to a <b>UNICODE_STRING</b> structure that contains the path name of a file that contains the registry hive information that is being loaded.


### -field Flags

Reserved for system use.


### -field TrustClassObject

Reserved for system use.


### -field UserEvent

A pointer to an event object that is signaled when the hive is unloaded.


### -field DesiredAccess

The access mask that was specified by the thread that is trying to load the registry key. For more information about this access mask, see the description of the <i>DesiredAccess</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> routine.


### -field RootHandle

An optional pointer to a location that receives the handle to the root of the hive that is being loaded. This member can be non-<b>NULL</b> if an application hive is  being loaded. In all other cases, this member should be <b>NULL</b>.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a> routine.


### -field Reserved

Reserved for system use.


## -remarks



The operating system passes the <b>REG_LOAD_KEY_INFORMATION</b> structure to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a user-mode thread calls <a href="https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regloadkeya">RegLoadKey</a> to load a registry hive.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regloadkeya">RegLoadKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>
 

 

