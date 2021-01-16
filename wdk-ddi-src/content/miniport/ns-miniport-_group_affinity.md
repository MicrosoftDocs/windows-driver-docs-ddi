---
UID: NS:miniport._GROUP_AFFINITY
title: _GROUP_AFFINITY (miniport.h)
description: The GROUP_AFFINITY structure specifies a group number and the processor affinity within that group.
old-location: kernel\group_affinity.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["GROUP_AFFINITY structure"]
ms.keywords: "*PGROUP_AFFINITY, GROUP_AFFINITY, GROUP_AFFINITY structure [Kernel-Mode Driver Architecture], PGROUP_AFFINITY, PGROUP_AFFINITY structure pointer [Kernel-Mode Driver Architecture], _GROUP_AFFINITY, kernel.group_affinity, kstruct_b_9d437322-c6bb-4579-8d7b-144a7513bbd9.xml, miniport/GROUP_AFFINITY, miniport/PGROUP_AFFINITY"
req.header: miniport.h
req.include-header: Winnt.h, Ntdef.h, Windef.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
targetos: Windows
req.typenames: GROUP_AFFINITY, *PGROUP_AFFINITY
f1_keywords:
 - _GROUP_AFFINITY
 - miniport/_GROUP_AFFINITY
 - PGROUP_AFFINITY
 - miniport/PGROUP_AFFINITY
 - GROUP_AFFINITY
 - miniport/GROUP_AFFINITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - miniport.h
api_name:
 - _GROUP_AFFINITY
 - PGROUP_AFFINITY
 - GROUP_AFFINITY
---

# _GROUP_AFFINITY structure (miniport.h)


## -description

The <b>GROUP_AFFINITY</b> structure specifies a group number and the processor <a href="/windows-hardware/drivers/">affinity</a> within that group.

## -struct-fields

### -field Mask

Specifies the affinity mask. This parameter is a [**KAFFINITY**](/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value. The bits in the affinity mask identify a set of processors within the group identified by <b>Group</b>.

### -field Group

Specifies the group number. In Windows 7, the group number must be in the range from 0 to 3.

### -field Reserved

Reserved for future use. Set all three <b>Reserved</b> array elements to zero.

## -remarks

This structure describes a group-specific affinity.

A <b>GROUP_AFFINITY</b> structure can describe a thread affinity, which is a set of processors on which a thread is allowed to run. All of the processors in this set belong to the group that is identified by the <b>Group</b> member of the structure. The <b>Mask</b> member contains an affinity mask that identifies the processors in the set. For example, the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemgroupaffinitythread">KeSetSystemGroupAffinityThread</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttousergroupaffinitythread">KeRevertToUserGroupAffinityThread</a> routines use <b>GROUP_AFFINITY</b> structures to specify thread affinities.

A <b>GROUP_AFFINITY</b> structure can describe an interrupt affinity, which is a set of processors on which an interrupt service routine can receive interrupts. For example, the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdevicenumanode">IoGetDeviceNumaNode</a> routine uses <b>GROUP_AFFINITY</b> structures to specify interrupt affinities.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdevicenumanode">IoGetDeviceNumaNode</a>



[**KAFFINITY**](/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttousergroupaffinitythread">KeRevertToUserGroupAffinityThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemgroupaffinitythread">KeSetSystemGroupAffinityThread</a>

