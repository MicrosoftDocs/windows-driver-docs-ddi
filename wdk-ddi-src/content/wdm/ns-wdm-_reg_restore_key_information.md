---
UID: NS:wdm._REG_RESTORE_KEY_INFORMATION
title: "_REG_RESTORE_KEY_INFORMATION"
author: windows-driver-content
description: The REG_RESTORE_KEY_INFORMATION structure contains the information for a registry key that is about to be restored.
old-location: kernel\reg_restore_key_information.htm
old-project: kernel
ms.assetid: df9180d8-37aa-4b75-a8c6-a786901bd8a6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/REG_RESTORE_KEY_INFORMATION, PREG_RESTORE_KEY_INFORMATION, wdm/PREG_RESTORE_KEY_INFORMATION, _REG_RESTORE_KEY_INFORMATION, REG_RESTORE_KEY_INFORMATION, REG_RESTORE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], *PREG_RESTORE_KEY_INFORMATION, PREG_RESTORE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], kernel.reg_restore_key_information, kstruct_d_493707cd-b5e8-4f28-b080-b3639060b5e9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista SP2 and later versions of the Windows operating system.
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
-	REG_RESTORE_KEY_INFORMATION
product: Windows
targetos: Windows
req.typenames: REG_RESTORE_KEY_INFORMATION, *PREG_RESTORE_KEY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_RESTORE_KEY_INFORMATION structure


## -description


The <b>REG_RESTORE_KEY_INFORMATION</b> structure contains the information for a registry key that is about to be restored.


## -syntax


````
typedef struct _REG_RESTORE_KEY_INFORMATION {
  PVOID  Object;
  HANDLE FileHandle;
  ULONG  Flags;
  PVOID  CallContext;
  PVOID  ObjectContext;
  PVOID  Reserved;
} REG_RESTORE_KEY_INFORMATION, *PREG_RESTORE_KEY_INFORMATION;
````


## -struct-fields




### -field Object

A pointer to a registry key object for the key whose name is about to be changed.


### -field FileHandle

A handle to the file from which the hive will be restored.


### -field Flags

<b>REG_FORCE_RESTORE</b>

0x00000008L

If specified, the restore operation is executed even if open handles exist at or beneath the location in the registry hierarchy to which the <i>hKey</i> parameter points.

<b>REG_WHOLE_HIVE_VOLATILE</b>

0x00000001L

If specified, a new, volatile (memory-only) set of registry information, or <i>hive</i>, is created. If REG_WHOLE_HIVE_VOLATILE is specified, the key identified by the <i>hKey</i> parameter must be either the HKEY_USERS or HKEY_LOCAL_MACHINE value.

<b>REG_REFRESH_HIVE</b>

0x00000002

If set, the location of the subtree that the <i>hKey</i> parameter points to is restored to its state immediately following the last flush. The subtree must not be lazy flushed (by calling <b>RegRestoreKey</b> with REG_NO_LAZY_FLUSH specified as the value of this parameter); the caller must have the trusted computing base (TCB) privilege; and the handle to which the <i>hKey</i> parameter refers must point to the root of the subtree.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information, which the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks


Note that when a key is restored, only the last component of the path can be changed.

The REG_REFRESH_HIVE flag is opaque and a filter should not attempt to change it.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_RESTORE_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

