---
UID: NS:pepfx._PEP_QUERY_SOC_SUBSYSTEM
title: "_PEP_QUERY_SOC_SUBSYSTEM"
author: windows-driver-content
description: The PEP_QUERY_SOC_SUBSYSTEM structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM notification to gather basic information about a particular system on a chip (SoC) subsystem.
old-location: kernel\pep_query_soc_subsystem.htm
old-project: kernel
ms.assetid: F4571085-19C2-46FD-B754-D4937BE5A500
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_QUERY_SOC_SUBSYSTEM, PEP_QUERY_SOC_SUBSYSTEM, PEP_QUERY_SOC_SUBSYSTEM structure [Kernel-Mode Driver Architecture], PPEP_QUERY_SOC_SUBSYSTEM, PPEP_QUERY_SOC_SUBSYSTEM structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_SOC_SUBSYSTEM, kernel.pep_query_soc_subsystem, pepfx/PEP_QUERY_SOC_SUBSYSTEM, pepfx/PPEP_QUERY_SOC_SUBSYSTEM"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_QUERY_SOC_SUBSYSTEM
product: Windows
targetos: Windows
req.typenames: PEP_QUERY_SOC_SUBSYSTEM, *PPEP_QUERY_SOC_SUBSYSTEM
---

# _PEP_QUERY_SOC_SUBSYSTEM structure


## -description


The <b>PEP_QUERY_SOC_SUBSYSTEM</b> structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186731">PEP_DPM_QUERY_SOC_SUBSYSTEM notification</a> to gather basic information about a particular system on a chip (SoC) subsystem.


## -syntax


````
typedef struct _PEP_QUERY_SOC_SUBSYSTEM {
  ULONG          PlatformIdleStateIndex;
  ULONG          SubsystemIndex;
  PVOID          SubsystemHandle;
  UNICODE_STRING ParentName;
  UNICODE_STRING SubsystemName;
  ULONG          MetadataCount;
  ULONG          Flags;
} PEP_QUERY_SOC_SUBSYSTEM, *PPEP_QUERY_SOC_SUBSYSTEM;
````


## -struct-fields




### -field PlatformIdleStateIndex

[in] The platform idle state index that is being queried by the kernel.


### -field SubsystemIndex

[in] The subsystem index, which is a unique index assigned by the OS to each subsystem within the context of a given <b>PlatformIdleStateIndex</b>. 

The kernel initializes this value to zero and increments it for each subsequent subsystem static info notification.  A value of 0 means it's the first such notification for the given <b>PlatformIdleStateIndex</b>.  This field is intended to give the PEP context between instances of this notification.  It is the only field whose input value varies across instances of this notification for a given <b>PlatformIdleStateIndex</b> and a PEP might use this value to look up a subsystem.  

The  PEP can ignore this value.  


### -field SubsystemHandle

[out] A context pointer that the PEP can optionally assign a value to. It will receive the pointer on subsequent notifications for this particular subsystem.  In subsequent notifications, a PEP uses <b>PlatformIdleStateIndex</b> along with <b>SubsystemName</b> and/or <b>SubsystemHandle</b> to look up a particular subsystemâ€™s accounting data. 

By default the value if this member is zero.  This value is ignored by the OS and used only in notifications.  

The PEP is not required to fill  this member.


### -field ParentName

[in/out]  A buffer for holding the parent name of the corresponding subsystem.  Each  subsystem has a parent and subsystems with the same value for <b>ParentName</b> are considered siblings.  Subsystem sibling hierarchies are optional.  In the absence of any hierarchy, all subsystems are top level subsystems and specify a common value for <b>ParentName</b>.  To indicate a hierarchy, top level subsystems specify a common <b>ParentName</b> while each non-top-level subsystem specifies its parent subsystemâ€™s <b>SubsystemName</b> for <b>ParentName</b>.  



Prior to entry, the kernel will:

<ul>
<li>Pre-allocate 64 <b>WCHARs</b> for <b>ParentName.Buffer[]</b></li>
<li>Zero the buffer </li>
<li>Set <b>ParentName.MaximumLength</b> to the size of the buffer in bytes, and </li>
<li>Set <b>ParentName.Length</b> = <b>0</b></li>
</ul>
 Prior to  exit, the PEP must copy a null-terminated string into <b>ParentName.Buffer</b> and update <b>ParentName.Length</b> with a byte count that is <b>sizeof(WCHAR)</b> times the number of UNICODE characters copied, not including the terminating <b>UNICODE_NULL</b>.  

The PEP must use the allocated memory that is pointed to by the address in <b>ParentName.Buffer</b> to provide the parent name. 
Since this memory is pre-allocated, its size cannot be changed. The PEP is responsible for truncating the parent name, if necessary, so that it does not exceed the length specified in <b>ParentName.MaximumLength</b> (including the terminating <b>UNICODE_NULL</b> character).


### -field SubsystemName

[in/out] A buffer for holding this subsystem's name.  Every subsystem has a subsystem name and <b>SubsystemName</b> must be unique among all subsystems within the context of a given platform idle state.  A subsystemâ€™s <b>SubsystemName</b> cannot be the same as <b>ParentName</b>.



Prior to entry, the kernel will:

<ul>
<li>Pre-allocate 64 <b>WCHARs</b> for <b>SubsystemName.Buffer[]</b></li>
<li>Zero the buffer </li>
<li>Set <b>SubsystemName.MaximumLength</b> to the size of the buffer in bytes, and </li>
<li>Set <b>SubsystemName.Length</b> = <b>0</b></li>
</ul>
Prior to exit, the PEP must copy a null-terminated string into <b>SubsystemName.Buffer</b> and update <b>SubsystemName.Length</b> with a byte count that is <b>sizeof(WCHAR)</b> times the number of UNICODE characters copied, not including the terminating <b>UNICODE_NULL</b>.  

The PEP must use the allocated memory that is pointed to by the address in <b>SubsystemName.Buffer</b> to provide the subsystem name. 
Since this memory is pre-allocated, its size cannot be changed. The PEP is responsible for truncating the subsystem name, if necessary, so that it does not exceed the length specified in <b>SubsystemName.MaximumLength</b> (including the terminating <b>UNICODE_NULL</b> character).


### -field MetadataCount

[out] The number of metadata key/value string pairs tallied by this SoC subsystem.  

Metadata is optional.  The PEP returns zero if it does not report any metadata for this SoC subsystem.


### -field Flags

This member is reserved and should be set to zero.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186731">PEP_DPM_QUERY_SOC_SUBSYSTEM notification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_QUERY_SOC_SUBSYSTEM structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

