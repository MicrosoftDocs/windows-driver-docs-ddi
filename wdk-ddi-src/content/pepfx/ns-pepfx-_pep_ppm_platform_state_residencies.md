---
UID: NS:pepfx._PEP_PPM_PLATFORM_STATE_RESIDENCIES
title: _PEP_PPM_PLATFORM_STATE_RESIDENCIES
author: windows-driver-content
description: The PEP_PPM_PLATFORM_STATE_RESIDENCIES structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.
old-location: kernel\pep_ppm_platform_state_residencies.htm
old-project: kernel
ms.assetid: 5B6186EB-EC08-4C11-9CCF-E07D78FBD535
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/PEP_PPM_PLATFORM_STATE_RESIDENCIES, PPEP_PPM_PLATFORM_STATE_RESIDENCIES, kernel.pep_ppm_platform_state_residencies, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES, PEP_PPM_PLATFORM_STATE_RESIDENCIES, PEP_PPM_PLATFORM_STATE_RESIDENCIES structure [Kernel-Mode Driver Architecture], PPEP_PPM_PLATFORM_STATE_RESIDENCIES structure pointer [Kernel-Mode Driver Architecture], pepfx/PPEP_PPM_PLATFORM_STATE_RESIDENCIES, _PEP_PPM_PLATFORM_STATE_RESIDENCIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	pepfx.h
apiname: 
-	PEP_PPM_PLATFORM_STATE_RESIDENCIES
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PLATFORM_STATE_RESIDENCIES, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES
---

# _PEP_PPM_PLATFORM_STATE_RESIDENCIES structure


## -description


The <b>PEP_PPM_PLATFORM_STATE_RESIDENCIES</b> structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.


## -syntax


````
typedef struct _PEP_PPM_PLATFORM_STATE_RESIDENCIES {
  ULONG                             Count;
  PPEP_PPM_PLATFORM_STATE_RESIDENCY States;
} PEP_PPM_PLATFORM_STATE_RESIDENCIES, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES;
````


## -struct-fields




### -field Count

[in] The number of elements in the array pointed to by the <b>States</b> member. The number of array elements equals the number of platform idle states that the PEP previously provided in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.


### -field States

[in] A pointer to an output buffer to which the PEP writes an array of <a href="..\pepfx\ns-pepfx-_pep_ppm_platform_state_residency.md">PEP_PPM_PLATFORM_STATE_RESIDENCY</a> structures. Each structure contains the accumulated residency and transition count information for a particular platform idle state. This buffer is guaranteed to be large enough to contain the number of array elements specified by the <b>Count</b> member. Each idle state is identified by its array index. If the array contains N elements, idle state indexes range from 0 to N-1.


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186817">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a> notification. Both members of the structure contain input values that the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) supplies when this notification is sent to the PEP. PoFx allocates the output buffer pointed to by the <b>States</b> member, and the PEP writes to this buffer.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186817">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a>

<a href="..\pepfx\ns-pepfx-_pep_ppm_platform_state_residency.md">PEP_PPM_PLATFORM_STATE_RESIDENCY</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PLATFORM_STATE_RESIDENCIES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

