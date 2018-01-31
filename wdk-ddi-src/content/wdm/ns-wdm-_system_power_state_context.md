---
UID: NS:wdm._SYSTEM_POWER_STATE_CONTEXT
title: "_SYSTEM_POWER_STATE_CONTEXT"
author: windows-driver-content
description: The SYSTEM_POWER_STATE_CONTEXT structure is a partially opaque system structure that contains information about the previous system power states of a computer.
old-location: kernel\system_power_state_context.htm
old-project: kernel
ms.assetid: C924C7BD-071C-4A98-9A9B-2BEFA1101DF3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PSYSTEM_POWER_STATE_CONTEXT, wdm/SYSTEM_POWER_STATE_CONTEXT, wdm/PSYSTEM_POWER_STATE_CONTEXT, kernel.system_power_state_context, _SYSTEM_POWER_STATE_CONTEXT, SYSTEM_POWER_STATE_CONTEXT structure [Kernel-Mode Driver Architecture], PSYSTEM_POWER_STATE_CONTEXT, PSYSTEM_POWER_STATE_CONTEXT structure pointer [Kernel-Mode Driver Architecture], SYSTEM_POWER_STATE_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	SYSTEM_POWER_STATE_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PSYSTEM_POWER_STATE_CONTEXT, SYSTEM_POWER_STATE_CONTEXT"
req.product: Windows 10 or later.
---

# _SYSTEM_POWER_STATE_CONTEXT structure


## -description


The <b>SYSTEM_POWER_STATE_CONTEXT</b> structure is a partially opaque system structure that contains information about the previous system power states of a computer.


## -syntax


````
typedef struct _SYSTEM_POWER_STATE_CONTEXT {
  union {
    struct {
      ULONG Reserved1  :8;
      ULONG TargetSystemState  :4;
      ULONG EffectiveSystemState  :4;
      ULONG CurrentSystemState  :4;
      ULONG IgnoreHibernationPath  :1;
      ULONG PseudoTransition  :1;
      ULONG Reserved2  :10;
    } DUMMYSTRUCTNAME;
    ULONG  ContextAsUlong;
  } DUMMYUNIONNAME;
} SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT;
````


## -struct-fields




#### - DUMMYUNIONNAME

Unnamed union.


#### DUMMYSTRUCTNAME

Unnamed structure.


#### ContextAsUlong

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

Unnamed structure.


#### DUMMYSTRUCTNAME.Reserved1

Opaque member. Reserved for system use.


#### DUMMYSTRUCTNAME.TargetSystemState

The target system power state of the previous <a href="https://msdn.microsoft.com/a37e8dda-af7a-4f28-bf04-908a74bb5b2f">system power IRP</a> that the driver received. This member is set to a <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a> enumeration value. Drivers should treat this member as read-only.


#### DUMMYSTRUCTNAME.EffectiveSystemState

The effective previous system power state, as perceived by the user. This member is set to a <b>SYSTEM_POWER_STATE</b> enumeration value. Drivers should treat this member as read-only. This member value might not match the <b>TargetSystemState</b> member if, for example, the previous system power IRP indicated that the computer was about to enter hibernation, but a hybrid shutdown instead occurred to prepare the computer for a fast startup. For more information, see Remarks.


#### DUMMYSTRUCTNAME.CurrentSystemState

Opaque member. Reserved for system use.


#### DUMMYSTRUCTNAME.IgnoreHibernationPath

Opaque member. Reserved for system use.


#### DUMMYSTRUCTNAME.PseudoTransition

Opaque member. Reserved for system use.


#### DUMMYSTRUCTNAME.Reserved2

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Reserved1

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.TargetSystemState

The target system power state of the previous <a href="https://msdn.microsoft.com/a37e8dda-af7a-4f28-bf04-908a74bb5b2f">system power IRP</a> that the driver received. This member is set to a <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a> enumeration value. Drivers should treat this member as read-only.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EffectiveSystemState

The effective previous system power state, as perceived by the user. This member is set to a <b>SYSTEM_POWER_STATE</b> enumeration value. Drivers should treat this member as read-only. This member value might not match the <b>TargetSystemState</b> member if, for example, the previous system power IRP indicated that the computer was about to enter hibernation, but a hybrid shutdown instead occurred to prepare the computer for a fast startup. For more information, see Remarks.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.CurrentSystemState

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.IgnoreHibernationPath

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.PseudoTransition

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.KernelSoftReboot

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Reserved2

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.ContextAsUlong

Opaque member. Reserved for system use.


## -remarks


Starting with Windows Vista, the <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a> in a <a href="https://msdn.microsoft.com/a37e8dda-af7a-4f28-bf04-908a74bb5b2f">system power IRP</a> contains a <b>SYSTEM_POWER_STATE_CONTEXT</b> structure. The <b>Power</b> member of the <b>IO_STACK_LOCATION</b> structure contains a <b>SystemPowerStateContext</b> member, which is a <b>SYSTEM_POWER_STATE_CONTEXT</b> structure. For more information, see <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>.

The size of the <b>SYSTEM_POWER_STATE_CONTEXT</b> structure is four bytes. This structure is divided into bit fields, most of which are opaque to drivers and reserved exclusively for use by the operating system. However, two of these bit fields, <b>TargetSystemState</b> and <b>EffectiveSystemState</b>, can be read by kernel-mode drivers to distinguish a fast startup from a wake-from-hibernation startup. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj835779">Distinguishing Fast Startup from Wake-from-Hibernation</a>.



## -see-also

<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>

<a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SYSTEM_POWER_STATE_CONTEXT structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

