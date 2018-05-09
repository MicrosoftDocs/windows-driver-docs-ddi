---
UID: NS:wdm._REG_POST_CREATE_KEY_INFORMATION
title: "_REG_POST_CREATE_KEY_INFORMATION"
author: windows-driver-content
description: The REG_POST_CREATE_KEY_INFORMATION structure contains the result of an attempt to create a registry key.
old-location: kernel\reg_post_create_key_information.htm
old-project: kernel
ms.assetid: bba965c9-7132-4988-bf89-b19004118c0a
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PREG_POST_CREATE_KEY_INFORMATION, *PREG_POST_OPEN_KEY_INFORMATION, PREG_POST_CREATE_KEY_INFORMATION, PREG_POST_CREATE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_POST_CREATE_KEY_INFORMATION, REG_POST_CREATE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], REG_POST_OPEN_KEY_INFORMATION, REG_POST_OPEN_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_POST_CREATE_KEY_INFORMATION, kernel.reg_post_create_key_information, kstruct_d_31e99ef7-d3dc-425d-9cc4-2735c50dd7dc.xml, wdm/PREG_POST_CREATE_KEY_INFORMATION, wdm/REG_POST_CREATE_KEY_INFORMATION, wdm/REG_POST_OPEN_KEY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available only on Microsoft Windows XP.
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
-	Wdm.h
api_name:
-	REG_POST_CREATE_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_POST_CREATE_KEY_INFORMATION, REG_POST_OPEN_KEY_INFORMATION, *PREG_POST_CREATE_KEY_INFORMATION, *PREG_POST_OPEN_KEY_INFORMATION
---

# _REG_POST_CREATE_KEY_INFORMATION structure


## -description


The <b>REG_POST_CREATE_KEY_INFORMATION</b> structure contains the result of an attempt to create a registry key.


## -struct-fields




### -field CompleteName

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that specifies the complete path of the registry key. 


### -field Object

A pointer to the registry key object that was created.


### -field Status

The NTSTATUS value that the system will return for the registry operation.


## -remarks



For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>
 

 

