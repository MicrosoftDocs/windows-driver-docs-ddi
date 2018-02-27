---
UID: NS:minitape._GROUP_AFFINITY
title: "_GROUP_AFFINITY"
author: windows-driver-content
description: The GROUP_AFFINITY structure specifies a group number and the processor affinity within that group.
old-location: kernel\group_affinity.htm
old-project: kernel
ms.assetid: 8a6fd914-94f9-4ccf-9b0a-cc102fd90965
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PGROUP_AFFINITY, GROUP_AFFINITY, GROUP_AFFINITY structure [Kernel-Mode Driver Architecture], PGROUP_AFFINITY, PGROUP_AFFINITY structure pointer [Kernel-Mode Driver Architecture], _GROUP_AFFINITY, kernel.group_affinity, kstruct_b_9d437322-c6bb-4579-8d7b-144a7513bbd9.xml, miniport/GROUP_AFFINITY, miniport/PGROUP_AFFINITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: minitape.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	miniport.h
api_name:
-	GROUP_AFFINITY
product: Windows
targetos: Windows
req.typenames: GROUP_AFFINITY, *PGROUP_AFFINITY
---

# _GROUP_AFFINITY structure


## -description


The <b>GROUP_AFFINITY</b> structure specifies a group number and the processor <a href="https://msdn.microsoft.com/4ef14b5b-128b-4b7c-9211-116e8bd60cab">affinity</a> within that group.


## -syntax


````
typedef struct _GROUP_AFFINITY {
  KAFFINITY Mask;
  WORD      Group;
  WORD      Reserved[3];
} GROUP_AFFINITY, *PGROUP_AFFINITY;
````


## -struct-fields




### -field Mask

Specifies the affinity mask. This parameter is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a> value. The bits in the affinity mask identify a set of processors within the group identified by <b>Group</b>.


### -field Group

Specifies the group number. In Windows 7, the group number must be in the range from 0 to 3.


### -field Reserved

Reserved for future use. Set all three <b>Reserved</b> array elements to zero. 


## -remarks



This structure describes a group-specific affinity.

A <b>GROUP_AFFINITY</b> structure can describe a thread affinity, which is a set of processors on which a thread is allowed to run. All of the processors in this set belong to the group that is identified by the <b>Group</b> member of the structure. The <b>Mask</b> member contains an affinity mask that identifies the processors in the set. For example, the <a href="..\wdm\nf-wdm-kesetsystemgroupaffinitythread.md">KeSetSystemGroupAffinityThread</a> and <a href="..\wdm\nf-wdm-kereverttousergroupaffinitythread.md">KeRevertToUserGroupAffinityThread</a> routines use <b>GROUP_AFFINITY</b> structures to specify thread affinities.

A <b>GROUP_AFFINITY</b> structure can describe an interrupt affinity, which is a set of processors on which an interrupt service routine can receive interrupts. For example, the <a href="..\wdm\nf-wdm-iogetdevicenumanode.md">IoGetDeviceNumaNode</a> routine uses <b>GROUP_AFFINITY</b> structures to specify interrupt affinities. 




## -see-also

<a href="..\wdm\nf-wdm-kesetsystemgroupaffinitythread.md">KeSetSystemGroupAffinityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="..\wdm\nf-wdm-iogetdevicenumanode.md">IoGetDeviceNumaNode</a>



<a href="..\wdm\nf-wdm-kereverttousergroupaffinitythread.md">KeRevertToUserGroupAffinityThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20GROUP_AFFINITY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

