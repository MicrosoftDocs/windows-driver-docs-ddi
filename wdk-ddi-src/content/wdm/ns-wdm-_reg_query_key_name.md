---
UID: NS:wdm._REG_QUERY_KEY_NAME
title: "_REG_QUERY_KEY_NAME"
author: windows-driver-content
description: The REG_QUERY_KEY_NAME structure describes the full registry key name of an object being queried.
old-location: kernel\reg_query_key_name.htm
old-project: kernel
ms.assetid: 396DA33D-46E0-456C-9FCF-85A7D9915F48
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: "*PREG_QUERY_KEY_NAME, PREG_QUERY_KEY_NAME, PREG_QUERY_KEY_NAME structure pointer [Kernel-Mode Driver Architecture], REG_QUERY_KEY_NAME, REG_QUERY_KEY_NAME structure [Kernel-Mode Driver Architecture], _REG_QUERY_KEY_NAME, kernel.reg_query_key_name, wdm/PREG_QUERY_KEY_NAME, wdm/REG_QUERY_KEY_NAME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows 10 and later versions of the Windows operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	REG_QUERY_KEY_NAME
product: Windows
targetos: Windows
req.typenames: REG_QUERY_KEY_NAME, *PREG_QUERY_KEY_NAME
---

# _REG_QUERY_KEY_NAME structure


## -description


The <b>REG_QUERY_KEY_NAME</b> structure describes the full registry key name
              of an object being queried.


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose metadata is about to be queried.


### -field ObjectNameInfo

A pointer to an <b>OBJECT_NAME_INFORMATION</b> structure (see wdm.h) that contains the full registry key name to be returned by the system, as a Unicode string.


### -field Length

Specifies the size, in bytes, of the <b>ObjectNameInfo</b> buffer.


### -field ReturnLength

 


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply.  


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>. It contains the key context for the key that is being queried.


### -field Reserved

This member is reserved for future use. 


#### - ResultLength

Pointer to a variable that receives (from the system) the amount of valid data, in bytes, in the <b>ObjectNameInfo</b> buffer.


## -remarks



The system passes this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to query the full name of the registry key. 

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also




<a href="https://msdn.microsoft.com/2ec47d47-1de3-43af-9a71-7fa366ba2d1a">REG_NOTIFY_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
 

 

