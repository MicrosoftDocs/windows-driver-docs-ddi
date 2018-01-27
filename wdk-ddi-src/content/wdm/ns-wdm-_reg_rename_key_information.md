---
UID: NS:wdm._REG_RENAME_KEY_INFORMATION
title: _REG_RENAME_KEY_INFORMATION
author: windows-driver-content
description: The REG_RENAME_KEY_INFORMATION structure contains the new name for a registry key whose name is about to be changed.
old-location: kernel\reg_rename_key_information.htm
old-project: kernel
ms.assetid: 80ffa1dc-aa4f-40b4-936b-7e441b3b123d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: REG_RENAME_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], kstruct_d_f6416cfd-5ace-4366-81a5-87b233551c7a.xml, kernel.reg_rename_key_information, PREG_RENAME_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _REG_RENAME_KEY_INFORMATION, REG_RENAME_KEY_INFORMATION, PREG_RENAME_KEY_INFORMATION, *PREG_RENAME_KEY_INFORMATION, wdm/PREG_RENAME_KEY_INFORMATION, wdm/REG_RENAME_KEY_INFORMATION
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wdm.h
apiname: 
-	REG_RENAME_KEY_INFORMATION
product: Windows
targetos: Windows
req.typenames: *PREG_RENAME_KEY_INFORMATION, REG_RENAME_KEY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_RENAME_KEY_INFORMATION structure


## -description


The <b>REG_RENAME_KEY_INFORMATION</b> structure contains the new name for a registry key whose name is about to be changed. 


## -syntax


````
typedef struct _REG_RENAME_KEY_INFORMATION {
  PVOID           Object;
  PUNICODE_STRING NewName;
  PVOID           CallContext;
  PVOID           ObjectContext;
  PVOID           Reserved;
} REG_RENAME_KEY_INFORMATION, *PREG_RENAME_KEY_INFORMATION;
````


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose name is about to be changed.


### -field NewName

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the new name for the registry key.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks


Note that when a key is renamed, only the last component of the path can be changed.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_RENAME_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

