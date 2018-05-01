---
UID: NE:wdm._REG_NOTIFY_CLASS
title: "_REG_NOTIFY_CLASS"
author: windows-driver-content
description: The REG_NOTIFY_CLASS enumeration type specifies the type of registry operation that the configuration manager is passing to a RegistryCallback routine.
old-location: kernel\reg_notify_class.htm
old-project: kernel
ms.assetid: 2ec47d47-1de3-43af-9a71-7fa366ba2d1a
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: MaxRegNtNotifyClass, REG_NOTIFY_CLASS, REG_NOTIFY_CLASS enumeration [Kernel-Mode Driver Architecture], RegNtCallbackObjectContextCleanup, RegNtDeleteKey, RegNtDeleteValueKey, RegNtEnumerateKey, RegNtEnumerateValueKey, RegNtKeyHandleClose, RegNtPostCreateKey, RegNtPostCreateKeyEx, RegNtPostDeleteKey, RegNtPostDeleteValueKey, RegNtPostEnumerateKey, RegNtPostEnumerateValueKey, RegNtPostFlushKey, RegNtPostKeyHandleClose, RegNtPostLoadKey, RegNtPostOpenKey, RegNtPostOpenKeyEx, RegNtPostQueryKey, RegNtPostQueryKeyName, RegNtPostQueryKeySecurity, RegNtPostQueryMultipleValueKey, RegNtPostQueryValueKey, RegNtPostRenameKey, RegNtPostReplaceKey, RegNtPostRestoreKey, RegNtPostSaveKey, RegNtPostSetInformationKey, RegNtPostSetKeySecurity, RegNtPostSetValueKey, RegNtPostUnLoadKey, RegNtPreCreateKey, RegNtPreCreateKeyEx, RegNtPreDeleteKey, RegNtPreDeleteValueKey, RegNtPreEnumerateKey, RegNtPreEnumerateValueKey, RegNtPreFlushKey, RegNtPreKeyHandleClose, RegNtPreLoadKey, RegNtPreOpenKey, RegNtPreOpenKeyEx, RegNtPreQueryKey, RegNtPreQueryKeyName, RegNtPreQueryKeySecurity, RegNtPreQueryMultipleValueKey, RegNtPreQueryValueKey, RegNtPreRenameKey, RegNtPreReplaceKey, RegNtPreRestoreKey, RegNtPreSaveKey, RegNtPreSetInformationKey, RegNtPreSetKeySecurity, RegNtPreSetValueKey, RegNtPreUnLoadKey, RegNtQueryKey, RegNtQueryMultipleValueKey, RegNtQueryValueKey, RegNtRenameKey, RegNtSetInformationKey, RegNtSetValueKey, _REG_NOTIFY_CLASS, kernel.reg_notify_class, sysenum_b6fa1e3a-74d4-4925-b7c9-60d905c48f50.xml, wdm/MaxRegNtNotifyClass, wdm/REG_NOTIFY_CLASS, wdm/RegNtCallbackObjectContextCleanup, wdm/RegNtDeleteKey, wdm/RegNtDeleteValueKey, wdm/RegNtEnumerateKey, wdm/RegNtEnumerateValueKey, wdm/RegNtKeyHandleClose, wdm/RegNtPostCreateKey, wdm/RegNtPostCreateKeyEx, wdm/RegNtPostDeleteKey, wdm/RegNtPostDeleteValueKey, wdm/RegNtPostEnumerateKey, wdm/RegNtPostEnumerateValueKey, wdm/RegNtPostFlushKey, wdm/RegNtPostKeyHandleClose, wdm/RegNtPostLoadKey, wdm/RegNtPostOpenKey, wdm/RegNtPostOpenKeyEx, wdm/RegNtPostQueryKey, wdm/RegNtPostQueryKeyName, wdm/RegNtPostQueryKeySecurity, wdm/RegNtPostQueryMultipleValueKey, wdm/RegNtPostQueryValueKey, wdm/RegNtPostRenameKey, wdm/RegNtPostReplaceKey, wdm/RegNtPostRestoreKey, wdm/RegNtPostSaveKey, wdm/RegNtPostSetInformationKey, wdm/RegNtPostSetKeySecurity, wdm/RegNtPostSetValueKey, wdm/RegNtPostUnLoadKey, wdm/RegNtPreCreateKey, wdm/RegNtPreCreateKeyEx, wdm/RegNtPreDeleteKey, wdm/RegNtPreDeleteValueKey, wdm/RegNtPreEnumerateKey, wdm/RegNtPreEnumerateValueKey, wdm/RegNtPreFlushKey, wdm/RegNtPreKeyHandleClose, wdm/RegNtPreLoadKey, wdm/RegNtPreOpenKey, wdm/RegNtPreOpenKeyEx, wdm/RegNtPreQueryKey, wdm/RegNtPreQueryKeyName, wdm/RegNtPreQueryKeySecurity, wdm/RegNtPreQueryMultipleValueKey, wdm/RegNtPreQueryValueKey, wdm/RegNtPreRenameKey, wdm/RegNtPreReplaceKey, wdm/RegNtPreRestoreKey, wdm/RegNtPreSaveKey, wdm/RegNtPreSetInformationKey, wdm/RegNtPreSetKeySecurity, wdm/RegNtPreSetValueKey, wdm/RegNtPreUnLoadKey, wdm/RegNtQueryKey, wdm/RegNtQueryMultipleValueKey, wdm/RegNtQueryValueKey, wdm/RegNtRenameKey, wdm/RegNtSetInformationKey, wdm/RegNtSetValueKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available for Windows XP and later versions of the Windows operating system, but some enumeration values are available only for specified later versions of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	REG_NOTIFY_CLASS
product: Windows
targetos: Windows
req.typenames: REG_NOTIFY_CLASS
---

# _REG_NOTIFY_CLASS enumeration


## -description


The <b>REG_NOTIFY_CLASS</b> enumeration type specifies the type of registry operation that the configuration manager is passing to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine.


## -enum-fields




### -field RegNtDeleteKey

Specifies that a thread is attempting to delete a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreDeleteKey

Specifies that a thread is attempting to delete a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtSetValueKey

Specifies that a thread is attempting to set a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreSetValueKey

Specifies that a thread is attempting to set a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtDeleteValueKey

Specifies that a thread is attempting to delete a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreDeleteValueKey

Specifies that a thread is attempting to delete a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtSetInformationKey

Specifies that a thread is attempting to set the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreSetInformationKey

Specifies that a thread is attempting to set the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtRenameKey

Specifies that a thread is attempting to rename a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreRenameKey

Specifies that a thread is attempting to rename a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtEnumerateKey

Specifies that a thread is attempting to enumerate a subkey of a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreEnumerateKey

Specifies that a thread is attempting to enumerate a subkey of a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtEnumerateValueKey

Specifies that a thread is attempting to enumerate a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreEnumerateValueKey

Specifies that a thread is attempting to enumerate a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtQueryKey

Specifies that a thread is attempting to read the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreQueryKey

Specifies that a thread is attempting to read the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtQueryValueKey

Specifies that a thread is attempting to read a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreQueryValueKey

Specifies that a thread is attempting to read a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtQueryMultipleValueKey

Specifies that a thread is attempting to query multiple value entries for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on only Windows XP.


### -field RegNtPreQueryMultipleValueKey

Specifies that a thread is attempting to query multiple value entries for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreCreateKey

Specifies that a thread is attempting to create a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtPostCreateKey

Specifies that a thread has successfully created a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtPreOpenKey

Specifies that a thread is attempting to open an existing key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtPostOpenKey

Specifies that a thread has successfully opened an existing key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtKeyHandleClose

Specifies that a thread is attempting to close a key handle. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreKeyHandleClose

Specifies that a thread is attempting to close a key handle. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system. Drivers can monitor this registry operation but they cannot block or modify it.


### -field RegNtPostDeleteKey

Specifies that the system has attempted to delete the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostSetValueKey

Specifies that the system has attempted to set a value entry for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostDeleteValueKey

Specifies that the system has attempted to delete a value entry for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostSetInformationKey

Specifies that the system has attempted to set the key's metadata. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostRenameKey

Specifies that the system has attempted to rename the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostEnumerateKey

Specifies that the system has attempted to enumerate the subkey of a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostEnumerateValueKey

Specifies that the system has attempted to enumerate the value entry of a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostQueryKey

Specifies that the system has attempted to query the metadata for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostQueryValueKey

Specifies that the system has attempted to query a value entry for the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostQueryMultipleValueKey

Specifies that the system has attempted to query multiple value entries for the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostKeyHandleClose

Specifies that the system has attempted to close a key handle. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreCreateKeyEx

Specifies that a thread is attempting to create a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostCreateKeyEx

Specifies that the system has attempted to create a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreOpenKeyEx

Specifies that a thread is attempting to open an existing key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostOpenKeyEx

Specifies that the system has attempted to open an existing key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreFlushKey

Specifies that a thread is attempting to write a key to disk. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostFlushKey

Specifies that the system has attempted to write a key to disk. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreLoadKey

Specifies that a thread is attempting to load a registry hive from a file. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostLoadKey

Specifies that the system has attempted to load a registry hive from a file. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreUnLoadKey

Specifies that a thread is attempting to unload a registry hive. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostUnLoadKey

Specifies that the system has attempted to unload a registry hive. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreQueryKeySecurity

Specifies that a thread is attempting to obtain a registry key's security information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostQueryKeySecurity

Specifies that a thread has attempted to obtain a registry key's security information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreSetKeySecurity

Specifies that a thread is attempting to set a registry key's security information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostSetKeySecurity

Specifies that a thread has attempted to set a registry key's security information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtCallbackObjectContextCleanup


      Specifies that the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff541928">CmUnRegisterCallback</a> or the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine has just finished processing a <b>RegNtPreKeyHandleClose</b> class value. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreRestoreKey

Specifies that a thread is attempting to restore a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system. 


### -field RegNtPostRestoreKey

Specifies that a thread has attempted to restore a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPreSaveKey

Specifies that a thread is attempting to save a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPostSaveKey

Specifies that a thread has attempted to save a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPreReplaceKey

Specifies that a thread is attempting to replace a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPostReplaceKey

Specifies that a thread has attempted to replace a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPreQueryKeyName

Specifies that a thread is attempting to obtain the full path of a registry key. Use this value on Windows 10 and later versions of the Windows operating system.


### -field RegNtPostQueryKeyName

Specifies that a thread has attempted to obtain the full path of a registry key. Use this value on Windows 10 and later versions of the Windows operating system.


### -field MaxRegNtNotifyClass

Specifies the maximum value in this enumeration type.


## -remarks



When the configuration manager calls a driver's <i>RegistryCallback</i> routine, it passes a <b>REG_NOTIFY_CLASS</b> enumeration value to the routine. The configuration manager also passes a notification-specific structure that contains information about the notification. For a list of these structures, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541928">CmUnRegisterCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
 

 

