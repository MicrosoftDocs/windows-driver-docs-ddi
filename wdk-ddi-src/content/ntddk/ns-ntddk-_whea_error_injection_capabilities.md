---
UID: NS:ntddk._WHEA_ERROR_INJECTION_CAPABILITIES
title: "_WHEA_ERROR_INJECTION_CAPABILITIES"
author: windows-driver-content
description: The WHEA_ERROR_INJECTION_CAPABILITIES union describes the types of hardware errors that can be injected into a hardware platform.
old-location: whea\whea_error_injection_capabilities.htm
old-project: whea
ms.assetid: 77f982e4-6f35-4d4a-9c00-9ae34eacfbd3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_ERROR_INJECTION_CAPABILITIES, PWHEA_ERROR_INJECTION_CAPABILITIES, PWHEA_ERROR_INJECTION_CAPABILITIES union pointer [WHEA Drivers and Applications], WHEA_ERROR_INJECTION_CAPABILITIES, WHEA_ERROR_INJECTION_CAPABILITIES union [WHEA Drivers and Applications], _WHEA_ERROR_INJECTION_CAPABILITIES, ntddk/PWHEA_ERROR_INJECTION_CAPABILITIES, ntddk/WHEA_ERROR_INJECTION_CAPABILITIES, whea.whea_error_injection_capabilities, whearef_f040c2a7-cded-4903-a19c-c1163870c010.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
api_name:
-	WHEA_ERROR_INJECTION_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_INJECTION_CAPABILITIES, *PWHEA_ERROR_INJECTION_CAPABILITIES
---

# _WHEA_ERROR_INJECTION_CAPABILITIES structure


## -description


The WHEA_ERROR_INJECTION_CAPABILITIES union describes the types of hardware errors that can be injected into a hardware platform.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field AsULONG

A ULONG representation of the contents of the WHEA_ERROR_INJECTION_CAPABILITIES union.


#### - IA64Corrected

A single bit that indicates that a corrected IA64 error can be injected into the hardware platform.


#### - IA64Fatal

A single bit that indicates that a fatal IA64 error can be injected into the hardware platform.


#### - IA64Recoverable

A single bit that indicates that a recoverable IA64 error can be injected into the hardware platform.


#### - IA64RecoverableCache

A single bit that indicates that a recoverable IA64 cache error can be injected into the hardware platform.


#### - IA64RecoverableRegFile

A single bit that indicates that a recoverable IA64 register file error can be injected into the hardware platform.


#### - MemoryCorrectable

A single bit that indicates that a correctable memory error can be injected into the hardware platform.


#### - MemoryUncorrectableFatal

A single bit that indicates that an uncorrectable fatal memory error can be injected into the hardware platform.


#### - MemoryUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal memory error can be injected into the hardware platform.


#### - PCIExpressCorrectable

A single bit that indicates that a correctable PCI Express (PCIe) error can be injected into the hardware platform.


#### - PCIExpressUncorrectableFatal

A single bit that indicates that an uncorrectable fatal PCI Express (PCIe) error can be injected into the hardware platform.


#### - PCIExpressUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal PCI Express (PCIe) error can be injected into the hardware platform.


#### - PlatformCorrectable

A single bit that indicates that a correctable platform error can be injected into the hardware platform.


#### - PlatformUncorrectableFatal

A single bit that indicates that an uncorrectable fatal platform error can be injected into the hardware platform.


#### - PlatformUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal platform error can be injected into the hardware platform.


#### - ProcessorCorrectable

A single bit that indicates that a correctable processor error can be injected into the hardware platform.


#### - ProcessorUncorrectableFatal

A single bit that indicates that an uncorrectable fatal processor error can be injected into the hardware platform.


#### - ProcessorUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal processor error can be injected into the hardware platform.


#### - Reserved

Reserved for system use.


## -remarks



A user-mode WHEA management application calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559516">WHEAErrorInjectionMethods::GetErrorInjectionCapabilitiesRtn</a> method to retrieve a WHEA_ERROR_INJECTION_CAPABILITIES union that describes the types of hardware errors that can be injected into the hardware platform. If a PSHED plug-in is registered to participate in error injection, the PSHED plug-in's <a href="https://msdn.microsoft.com/8cb19677-11b8-4594-b4dd-ebd00fae07d4">GetInjectionCapabilities</a> callback function is called to provide this information back to the calling application. The application uses this information when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559518">WHEAErrorInjectionMethods::InjectErrorRtn</a> method to inject a hardware error into the hardware platform.




## -see-also




<a href="https://msdn.microsoft.com/8cb19677-11b8-4594-b4dd-ebd00fae07d4">GetInjectionCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559516">WHEAErrorInjectionMethods::GetErrorInjectionCapabilitiesRtn</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559518">WHEAErrorInjectionMethods::InjectErrorRtn</a>
 

 

