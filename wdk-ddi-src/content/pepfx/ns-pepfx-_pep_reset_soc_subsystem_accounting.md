---
UID: NS:pepfx._PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING
title: "_PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING"
author: windows-driver-content
description: The PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure is provided to the platform extension plug-in (PEP) as part of a PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification.
old-location: kernel\pep_reset_soc_subsystem_accounting.htm
old-project: kernel
ms.assetid: DCB0E541-51AB-4624-A007-46D109F31E5B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure [Kernel-Mode Driver Architecture], PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure pointer [Kernel-Mode Driver Architecture], pepfx/PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, pepfx/PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, _PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, kernel.pep_reset_soc_subsystem_accounting, *PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING
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
-	PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING
product: Windows
targetos: Windows
req.typenames: "*PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING"
---

# _PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure


## -description


The <b>PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING</b> structure is provided to the platform extension plug-in (PEP) as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186740">PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification</a>. 


## -syntax


````
typedef struct _PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING {
  ULONG PlatformIdleStateIndex;
  ULONG Flags;
} PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, *PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING;
````


## -struct-fields




### -field PlatformIdleStateIndex

[in] The platform idle state index for the subsystem accounting to be reset.


### -field Flags

This member is reserved and should be set to zero.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186740">PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

