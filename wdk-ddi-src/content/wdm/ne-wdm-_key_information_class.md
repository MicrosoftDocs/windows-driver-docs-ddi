---
UID: NE:wdm._KEY_INFORMATION_CLASS
title: "_KEY_INFORMATION_CLASS"
author: windows-driver-content
description: The KEY_INFORMATION_CLASS enumeration type represents the type of information to supply about a registry key.
old-location: kernel\key_information_class.htm
tech.root: kernel
ms.assetid: cb531a0e-c934-4f3e-9b92-07eb3ab75673
ms.date: 04/30/2018
ms.keywords: KEY_INFORMATION_CLASS, KEY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], KeyBasicInformation, KeyCachedInformation, KeyFlagsInformation, KeyFullInformation, KeyHandleTagsInformation, KeyNameInformation, KeyNodeInformation, KeyVirtualizationInformation, MaxKeyInfoClass, _KEY_INFORMATION_CLASS, kernel.key_information_class, sysenum_c64ec9c8-1eda-495a-8b4a-566607e29a78.xml, wdm/KEY_INFORMATION_CLASS, wdm/KeyBasicInformation, wdm/KeyCachedInformation, wdm/KeyFlagsInformation, wdm/KeyFullInformation, wdm/KeyHandleTagsInformation, wdm/KeyNameInformation, wdm/KeyNodeInformation, wdm/KeyVirtualizationInformation, wdm/MaxKeyInfoClass
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	KEY_INFORMATION_CLASS
product:
- Windows
targetos: Windows
req.typenames: KEY_INFORMATION_CLASS
---

# _KEY_INFORMATION_CLASS enumeration


## -description


The <b>KEY_INFORMATION_CLASS</b> enumeration type represents the type of information to supply about a registry key.


## -enum-fields




### -field KeyBasicInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a> structure is supplied.


### -field KeyNodeInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a> structure is supplied.


### -field KeyFullInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a> structure is supplied.


### -field KeyNameInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a> structure is supplied.


### -field KeyCachedInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a> structure is supplied.


### -field KeyFlagsInformation

Reserved for system use.


### -field KeyVirtualizationInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a> structure is supplied.


### -field KeyHandleTagsInformation

Reserved for system use.


### -field KeyTrustInformation


### -field KeyLayerInformation


### -field MaxKeyInfoClass

The maximum value in this enumeration type.


## -remarks



Use the <b>KEY_INFORMATION_CLASS</b> values to specify the type of data to be supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a> routines.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>
 

 

