---
UID: NS:ntpoapi._SYSTEM_POWER_STATE_CONTEXT
title: _SYSTEM_POWER_STATE_CONTEXT (ntpoapi.h)
description: The SYSTEM_POWER_STATE_CONTEXT structure is a partially opaque system structure that contains information about the previous system power states of a computer.
old-location: kernel\system_power_state_context.htm
tech.root: kernel
ms.assetid: C924C7BD-071C-4A98-9A9B-2BEFA1101DF3
ms.date: 04/30/2018
ms.keywords: "*PSYSTEM_POWER_STATE_CONTEXT, PSYSTEM_POWER_STATE_CONTEXT, PSYSTEM_POWER_STATE_CONTEXT structure pointer [Kernel-Mode Driver Architecture], SYSTEM_POWER_STATE_CONTEXT, SYSTEM_POWER_STATE_CONTEXT structure [Kernel-Mode Driver Architecture], _SYSTEM_POWER_STATE_CONTEXT, kernel.system_power_state_context, wdm/PSYSTEM_POWER_STATE_CONTEXT, wdm/SYSTEM_POWER_STATE_CONTEXT"
f1_keywords:
 - "ntpoapi/SYSTEM_POWER_STATE_CONTEXT"
req.header: ntpoapi.h
req.include-header: Ntpoapi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- SYSTEM_POWER_STATE_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# _SYSTEM_POWER_STATE_CONTEXT structure


## -description


The <b>SYSTEM_POWER_STATE_CONTEXT</b> structure is a partially opaque system structure that contains information about the previous system power states of a computer.


## -struct-fields




### -field DUMMYUNIONNAME

Unnamed union.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

Unnamed structure.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Reserved1

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.TargetSystemState

The target system power state of the previous <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-irps-for-the-system">system power IRP</a> that the driver received. This member is set to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a> enumeration value. Drivers should treat this member as read-only.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EffectiveSystemState

The effective previous system power state, as perceived by the user. This member is set to a <b>SYSTEM_POWER_STATE</b> enumeration value. Drivers should treat this member as read-only. This member value might not match the <b>TargetSystemState</b> member if, for example, the previous system power IRP indicated that the computer was about to enter hibernation, but a hybrid shutdown instead occurred to prepare the computer for a fast startup. For more information, see Remarks.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.CurrentSystemState

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.IgnoreHibernationPath

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.PseudoTransition

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.KernelSoftReboot

 
### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.DirectedDripsTransition
a Directed DRIPS transition.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Reserved2

Opaque member. Reserved for system use.


### -field DUMMYUNIONNAME.ContextAsUlong

Opaque member. Reserved for system use.


## -remarks



Starting with Windows Vista, the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-stack-locations">I/O stack location</a> in a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-irps-for-the-system">system power IRP</a> contains a <b>SYSTEM_POWER_STATE_CONTEXT</b> structure. The <b>Power</b> member of the <b>IO_STACK_LOCATION</b> structure contains a <b>SystemPowerStateContext</b> member, which is a <b>SYSTEM_POWER_STATE_CONTEXT</b> structure. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>.

The size of the <b>SYSTEM_POWER_STATE_CONTEXT</b> structure is four bytes. This structure is divided into bit fields, most of which are opaque to drivers and reserved exclusively for use by the operating system. However, two of these bit fields, <b>TargetSystemState</b> and <b>EffectiveSystemState</b>, can be read by kernel-mode drivers to distinguish a fast startup from a wake-from-hibernation startup. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation">Distinguishing Fast Startup from Wake-from-Hibernation</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a>
 

 

