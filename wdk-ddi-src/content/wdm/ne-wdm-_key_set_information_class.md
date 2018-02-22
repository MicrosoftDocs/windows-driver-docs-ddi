---
UID: NE:wdm._KEY_SET_INFORMATION_CLASS
title: "_KEY_SET_INFORMATION_CLASS"
author: windows-driver-content
description: The KEY_SET_INFORMATION_CLASS enumeration type represents the type of information to set for a registry key.
old-location: kernel\key_set_information_class.htm
old-project: kernel
ms.assetid: 95a8f683-642c-4f33-9536-08f497567f87
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeyWow64FlagsInformation, sysenum_b2121228-e221-424c-8e84-cd213d91716b.xml, wdm/KeySetVirtualizationInformation, KeyControlFlagsInformation, kernel.key_set_information_class, wdm/KeyControlFlagsInformation, wdm/KEY_SET_INFORMATION_CLASS, wdm/KeyWriteTimeInformation, wdm/KeyWow64FlagsInformation, KeyWriteTimeInformation, KeySetHandleTagsInformation, wdm/KeySetHandleTagsInformation, KeySetVirtualizationInformation, MaxKeySetInfoClass, KEY_SET_INFORMATION_CLASS, wdm/MaxKeySetInfoClass, _KEY_SET_INFORMATION_CLASS, KeySetDebugInformation, KEY_SET_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], wdm/KeySetDebugInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	KEY_SET_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: KEY_SET_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _KEY_SET_INFORMATION_CLASS enumeration


## -description


The <b>KEY_SET_INFORMATION_CLASS</b> enumeration type represents the type of information to set for a registry key.


## -syntax


````
typedef enum _KEY_SET_INFORMATION_CLASS { 
  KeyWriteTimeInformation,
  KeyWow64FlagsInformation,
  KeyControlFlagsInformation,
  KeySetVirtualizationInformation,
  KeySetDebugInformation,
  KeySetHandleTagsInformation,
  MaxKeySetInfoClass
} KEY_SET_INFORMATION_CLASS;
````


## -enum-fields




### -field KeyWriteTimeInformation

Indicates that a <a href="..\wdm\ns-wdm-_key_write_time_information.md">KEY_WRITE_TIME_INFORMATION</a> structure is supplied.


### -field KeyWow64FlagsInformation

Reserved for system use.


### -field KeyControlFlagsInformation

Reserved for system use.


### -field KeySetVirtualizationInformation

Reserved for system use.


### -field KeySetDebugInformation

Reserved for system use.


### -field KeySetHandleTagsInformation

Reserved for system use.


### -field KeySetLayerInformation


### -field MaxKeySetInfoClass

This member constant is always the maximum value in the enumeration.


## -remarks



A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can receive a pointer to a <b>KEY_SET_INFORMATION_CLASS</b> structure as an input parameter.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="..\wdm\ns-wdm-_key_write_time_information.md">KEY_WRITE_TIME_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_SET_INFORMATION_CLASS enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

