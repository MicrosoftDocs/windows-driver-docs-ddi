---
UID: NE:wdm._REG_NOTIFY_CLASS
title: "_REG_NOTIFY_CLASS"
author: windows-driver-content
description: The REG_NOTIFY_CLASS enumeration type specifies the type of registry operation that the configuration manager is passing to a RegistryCallback routine.
old-location: kernel\reg_notify_class.htm
old-project: kernel
ms.assetid: 2ec47d47-1de3-43af-9a71-7fa366ba2d1a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_REG_NOTIFY_CLASS, wdm/RegNtPreCreateKey, RegNtPostRenameKey, RegNtPreReplaceKey, RegNtQueryMultipleValueKey, RegNtPostFlushKey, wdm/RegNtPreQueryKeyName, RegNtPreQueryKeyName, RegNtPostSaveKey, wdm/RegNtPostSaveKey, RegNtCallbackObjectContextCleanup, wdm/RegNtPostQueryValueKey, wdm/RegNtPreRenameKey, wdm/RegNtPreLoadKey, wdm/RegNtPostQueryMultipleValueKey, wdm/RegNtSetValueKey, RegNtQueryValueKey, RegNtPostSetKeySecurity, RegNtEnumerateValueKey, wdm/RegNtQueryValueKey, wdm/RegNtRenameKey, RegNtPostReplaceKey, wdm/REG_NOTIFY_CLASS, RegNtPreSetInformationKey, wdm/RegNtPreEnumerateKey, RegNtKeyHandleClose, RegNtPostRestoreKey, RegNtPostQueryKeyName, RegNtPostQueryKey, wdm/RegNtPostCreateKeyEx, kernel.reg_notify_class, wdm/RegNtPreOpenKey, wdm/RegNtDeleteKey, RegNtDeleteKey, RegNtPostQueryMultipleValueKey, RegNtRenameKey, wdm/RegNtPreSetInformationKey, wdm/RegNtEnumerateKey, wdm/RegNtPostRenameKey, sysenum_b6fa1e3a-74d4-4925-b7c9-60d905c48f50.xml, wdm/RegNtPreRestoreKey, wdm/RegNtCallbackObjectContextCleanup, wdm/RegNtPreQueryMultipleValueKey, RegNtPreEnumerateValueKey, RegNtPostSetValueKey, wdm/RegNtPreOpenKeyEx, RegNtQueryKey, wdm/RegNtPostSetValueKey, RegNtPostSetInformationKey, RegNtPreFlushKey, MaxRegNtNotifyClass, wdm/RegNtSetInformationKey, RegNtPreQueryKey, wdm/RegNtPreUnLoadKey, RegNtPreDeleteValueKey, RegNtPreCreateKeyEx, wdm/RegNtPostLoadKey, wdm/RegNtPreDeleteValueKey, wdm/RegNtPostOpenKeyEx, wdm/RegNtPreReplaceKey, RegNtPreQueryMultipleValueKey, RegNtPostQueryValueKey, RegNtPostUnLoadKey, wdm/RegNtPostQueryKey, wdm/RegNtQueryKey, RegNtSetInformationKey, RegNtPreQueryKeySecurity, RegNtPostOpenKey, wdm/RegNtDeleteValueKey, wdm/RegNtPostSetInformationKey, wdm/RegNtPostDeleteValueKey, wdm/RegNtPreQueryKey, RegNtSetValueKey, wdm/RegNtPostDeleteKey, wdm/RegNtEnumerateValueKey, wdm/RegNtPostQueryKeyName, RegNtPreRenameKey, RegNtPreQueryValueKey, RegNtPostDeleteValueKey, wdm/RegNtPreFlushKey, REG_NOTIFY_CLASS enumeration [Kernel-Mode Driver Architecture], wdm/RegNtKeyHandleClose, RegNtPostLoadKey, RegNtPreRestoreKey, wdm/RegNtPostKeyHandleClose, RegNtEnumerateKey, RegNtPostDeleteKey, wdm/RegNtPostEnumerateKey, wdm/RegNtPreSaveKey, wdm/RegNtPreSetValueKey, RegNtPostEnumerateKey, RegNtPostEnumerateValueKey, REG_NOTIFY_CLASS, RegNtPostCreateKeyEx, RegNtPreOpenKey, wdm/RegNtPostEnumerateValueKey, RegNtPreUnLoadKey, wdm/RegNtPostSetKeySecurity, wdm/RegNtPreKeyHandleClose, wdm/RegNtPreCreateKeyEx, wdm/MaxRegNtNotifyClass, wdm/RegNtPostOpenKey, RegNtPostCreateKey, RegNtPreSetValueKey, wdm/RegNtPreDeleteKey, RegNtPostKeyHandleClose, RegNtPreLoadKey, wdm/RegNtQueryMultipleValueKey, RegNtPreKeyHandleClose, wdm/RegNtPreQueryKeySecurity, wdm/RegNtPostReplaceKey, wdm/RegNtPostQueryKeySecurity, RegNtPostQueryKeySecurity, wdm/RegNtPostUnLoadKey, wdm/RegNtPreSetKeySecurity, wdm/RegNtPostRestoreKey, RegNtPreSetKeySecurity, wdm/RegNtPostCreateKey, RegNtPreOpenKeyEx, RegNtDeleteValueKey, RegNtPreDeleteKey, RegNtPreCreateKey, wdm/RegNtPreEnumerateValueKey, RegNtPostOpenKeyEx, wdm/RegNtPostFlushKey, wdm/RegNtPreQueryValueKey, RegNtPreSaveKey, RegNtPreEnumerateKey"
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
-	REG_NOTIFY_CLASS
product: Windows
targetos: Windows
req.typenames: REG_NOTIFY_CLASS
req.product: Windows 10 or later.
---

# _REG_NOTIFY_CLASS enumeration


## -description


The <b>REG_NOTIFY_CLASS</b> enumeration type specifies the type of registry operation that the configuration manager is passing to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine.


## -syntax


````
enum REG_NOTIFY_CLASS {
  RegNtDeleteKey, 
  RegNtPreDeleteKey                  = RegNtDeleteKey, 
  RegNtSetValueKey, 
  RegNtPreSetValueKey                = RegNtSetValueKey, 
  RegNtDeleteValueKey, 
  RegNtPreDeleteValueKey             = RegNtDeleteValueKey, 
  RegNtSetInformationKey, 
  RegNtPreSetInformationKey          = RegNtSetInformationKey, 
  RegNtRenameKey, 
  RegNtPreRenameKey                  = RegNtRenameKey, 
  RegNtEnumerateKey, 
  RegNtPreEnumerateKey               = RegNtEnumerateKey, 
  RegNtEnumerateValueKey, 
  RegNtPreEnumerateValueKey          = RegNtEnumerateValueKey, 
  RegNtQueryKey, 
  RegNtPreQueryKey                   = RegNtQueryKey, 
  RegNtQueryValueKey, 
  RegNtPreQueryValueKey              = RegNtQueryValueKey, 
  RegNtQueryMultipleValueKey, 
  RegNtPreQueryMultipleValueKey      = RegNtQueryMultipleValueKey, 
  RegNtPreCreateKey, 
  RegNtPostCreateKey, 
  RegNtPreOpenKey, 
  RegNtPostOpenKey, 
  RegNtKeyHandleClose, 
  RegNtPreKeyHandleClose             = RegNtKeyHandleClose, 
  RegNtPostDeleteKey, 
  RegNtPostSetValueKey, 
  RegNtPostDeleteValueKey, 
  RegNtPostSetInformationKey, 
  RegNtPostRenameKey, 
  RegNtPostEnumerateKey, 
  RegNtPostEnumerateValueKey, 
  RegNtPostQueryKey, 
  RegNtPostQueryValueKey, 
  RegNtPostQueryMultipleValueKey, 
  RegNtPostKeyHandleClose, 
  RegNtPreCreateKeyEx, 
  RegNtPostCreateKeyEx, 
  RegNtPreOpenKeyEx, 
  RegNtPostOpenKeyEx, 
  RegNtPreFlushKey, 
  RegNtPostFlushKey, 
  RegNtPreLoadKey, 
  RegNtPostLoadKey, 
  RegNtPreUnLoadKey, 
  RegNtPostUnLoadKey, 
  RegNtPreQueryKeySecurity, 
  RegNtPostQueryKeySecurity, 
  RegNtPreSetKeySecurity, 
  RegNtPostSetKeySecurity, 
  RegNtCallbackObjectContextCleanup, 
  RegNtPreRestoreKey, 
  RegNtPostRestoreKey, 
  RegNtPreSaveKey, 
  RegNtPostSaveKey, 
  RegNtPreReplaceKey, 
  RegNtPostReplaceKey, 
  RegNtPreQueryKeyName, 
  RegNtPostQueryKeyName, 
  MaxRegNtNotifyClass 

};
````


## -enum-fields




#### - RegNtDeleteKey

Specifies that a thread is attempting to delete a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreDeleteKey

Specifies that a thread is attempting to delete a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtSetValueKey

Specifies that a thread is attempting to set a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreSetValueKey

Specifies that a thread is attempting to set a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtDeleteValueKey

Specifies that a thread is attempting to delete a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreDeleteValueKey

Specifies that a thread is attempting to delete a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtSetInformationKey

Specifies that a thread is attempting to set the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreSetInformationKey

Specifies that a thread is attempting to set the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtRenameKey

Specifies that a thread is attempting to rename a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreRenameKey

Specifies that a thread is attempting to rename a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtEnumerateKey

Specifies that a thread is attempting to enumerate a subkey of a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreEnumerateKey

Specifies that a thread is attempting to enumerate a subkey of a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtEnumerateValueKey

Specifies that a thread is attempting to enumerate a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreEnumerateValueKey

Specifies that a thread is attempting to enumerate a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtQueryKey

Specifies that a thread is attempting to read the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreQueryKey

Specifies that a thread is attempting to read the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtQueryValueKey

Specifies that a thread is attempting to read a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreQueryValueKey

Specifies that a thread is attempting to read a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtQueryMultipleValueKey

Specifies that a thread is attempting to query multiple value entries for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on only Windows XP.


#### - RegNtPreQueryMultipleValueKey

Specifies that a thread is attempting to query multiple value entries for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPreCreateKey

Specifies that a thread is attempting to create a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


#### - RegNtPostCreateKey

Specifies that a thread has successfully created a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


#### - RegNtPreOpenKey

Specifies that a thread is attempting to open an existing key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


#### - RegNtPostOpenKey

Specifies that a thread has successfully opened an existing key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


#### - RegNtKeyHandleClose

Specifies that a thread is attempting to close a key handle. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


#### - RegNtPreKeyHandleClose

Specifies that a thread is attempting to close a key handle. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system. Drivers can monitor this registry operation but they cannot block or modify it.


#### - RegNtPostDeleteKey

Specifies that the system has attempted to delete the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostSetValueKey

Specifies that the system has attempted to set a value entry for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostDeleteValueKey

Specifies that the system has attempted to delete a value entry for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostSetInformationKey

Specifies that the system has attempted to set the key's metadata. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostRenameKey

Specifies that the system has attempted to rename the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostEnumerateKey

Specifies that the system has attempted to enumerate the subkey of a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostEnumerateValueKey

Specifies that the system has attempted to enumerate the value entry of a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostQueryKey

Specifies that the system has attempted to query the metadata for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostQueryValueKey

Specifies that the system has attempted to query a value entry for the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostQueryMultipleValueKey

Specifies that the system has attempted to query multiple value entries for the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostKeyHandleClose

Specifies that the system has attempted to close a key handle. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPreCreateKeyEx

Specifies that a thread is attempting to create a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostCreateKeyEx

Specifies that the system has attempted to create a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPreOpenKeyEx

Specifies that a thread is attempting to open an existing key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPostOpenKeyEx

Specifies that the system has attempted to open an existing key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


#### - RegNtPreFlushKey

Specifies that a thread is attempting to write a key to disk. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPostFlushKey

Specifies that the system has attempted to write a key to disk. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPreLoadKey

Specifies that a thread is attempting to load a registry hive from a file. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPostLoadKey

Specifies that the system has attempted to load a registry hive from a file. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPreUnLoadKey

Specifies that a thread is attempting to unload a registry hive. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPostUnLoadKey

Specifies that the system has attempted to unload a registry hive. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPreQueryKeySecurity

Specifies that a thread is attempting to obtain a registry key's security information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPostQueryKeySecurity

Specifies that a thread has attempted to obtain a registry key's security information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPreSetKeySecurity

Specifies that a thread is attempting to set a registry key's security information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPostSetKeySecurity

Specifies that a thread has attempted to set a registry key's security information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtCallbackObjectContextCleanup


      Specifies that the driver has called <a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a> or the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine has just finished processing a <b>RegNtPreKeyHandleClose</b> class value. Use this value on Windows Vista and later versions of the Windows operating system.


#### - RegNtPreRestoreKey

Specifies that a thread is attempting to restore a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system. 


#### - RegNtPostRestoreKey

Specifies that a thread has attempted to restore a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


#### - RegNtPreSaveKey

Specifies that a thread is attempting to save a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


#### - RegNtPostSaveKey

Specifies that a thread has attempted to save a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


#### - RegNtPreReplaceKey

Specifies that a thread is attempting to replace a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


#### - RegNtPostReplaceKey

Specifies that a thread has attempted to replace a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


#### - RegNtPreQueryKeyName

Specifies that a thread is attempting to obtain the full path of a registry key. Use this value on Windows 10 and later versions of the Windows operating system.


#### - RegNtPostQueryKeyName

Specifies that a thread has attempted to obtain the full path of a registry key. Use this value on Windows 10 and later versions of the Windows operating system.


#### - MaxRegNtNotifyClass

Specifies the maximum value in this enumeration type.


## -remarks


When the configuration manager calls a driver's <i>RegistryCallback</i> routine, it passes a <b>REG_NOTIFY_CLASS</b> enumeration value to the routine. The configuration manager also passes a notification-specific structure that contains information about the notification. For a list of these structures, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_NOTIFY_CLASS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

