---
UID: NS:wdm._REG_QUERY_KEY_INFORMATION
title: "_REG_QUERY_KEY_INFORMATION"
author: windows-driver-content
description: The REG_QUERY_KEY_INFORMATION structure describes the metadata that is about to be queried for a key.
old-location: kernel\reg_query_key_information.htm
old-project: kernel
ms.assetid: 88c64e9a-dbf2-4feb-9ce2-615b5ba98439
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PREG_QUERY_KEY_INFORMATION, PREG_QUERY_KEY_INFORMATION, PREG_QUERY_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_QUERY_KEY_INFORMATION, REG_QUERY_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_QUERY_KEY_INFORMATION, kernel.reg_query_key_information, kstruct_d_5e665782-95c2-4fca-bd49-cb364c449540.xml, wdm/PREG_QUERY_KEY_INFORMATION, wdm/REG_QUERY_KEY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	REG_QUERY_KEY_INFORMATION
product: Windows
targetos: Windows
req.typenames: REG_QUERY_KEY_INFORMATION, *PREG_QUERY_KEY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_QUERY_KEY_INFORMATION structure


## -description


The <b>REG_QUERY_KEY_INFORMATION</b> structure describes the metadata that is about to be queried for a key.


## -syntax


````
typedef struct _REG_QUERY_KEY_INFORMATION {
  PVOID                 Object;
  KEY_INFORMATION_CLASS KeyInformationClass;
  PVOID                 KeyInformation;
  ULONG                 Length;
  PULONG                ResultLength;
  PVOID                 CallContext;
  PVOID                 ObjectContext;
  PVOID                 Reserved;
} REG_QUERY_KEY_INFORMATION, *PREG_QUERY_KEY_INFORMATION;
````


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose metadata is about to be queried.


### -field KeyInformationClass

The <a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a> value that indicates the type of information to be returned by the system.


### -field KeyInformation

A pointer to a buffer that contains the information to be returned by the system. The format of the buffer depends on the value of <b>KeyInformationClass</b>. For more information see <a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a>.


### -field Length

Specifies the size, in bytes, of the <b>KeyInformation</b> buffer.


### -field ResultLength

Pointer to a variable that receives (from the system) the amount of valid data, in bytes, in the <b>KeyInformation</b> buffer.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system. 


## -remarks



The system passes this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to query the metadata for a key—for example, when a user-mode thread calls <b>RegQueryInfoKey</b> or when a driver calls <a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a>



<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



 

 


