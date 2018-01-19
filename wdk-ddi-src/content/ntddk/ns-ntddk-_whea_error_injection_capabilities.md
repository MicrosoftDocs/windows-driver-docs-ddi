---
UID: NS:ntddk._WHEA_ERROR_INJECTION_CAPABILITIES
title: _WHEA_ERROR_INJECTION_CAPABILITIES
author: windows-driver-content
description: The WHEA_ERROR_INJECTION_CAPABILITIES union describes the types of hardware errors that can be injected into a hardware platform.
old-location: whea\whea_error_injection_capabilities.htm
old-project: whea
ms.assetid: 77f982e4-6f35-4d4a-9c00-9ae34eacfbd3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_ERROR_INJECTION_CAPABILITIES, *PWHEA_ERROR_INJECTION_CAPABILITIES, WHEA_ERROR_INJECTION_CAPABILITIES
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
req.alt-api: WHEA_ERROR_INJECTION_CAPABILITIES
req.alt-loc: ntddk.h
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
req.typenames: *PWHEA_ERROR_INJECTION_CAPABILITIES, WHEA_ERROR_INJECTION_CAPABILITIES
---

# _WHEA_ERROR_INJECTION_CAPABILITIES structure



## -description
The WHEA_ERROR_INJECTION_CAPABILITIES union describes the types of hardware errors that can be injected into a hardware platform.



## -syntax

````
typedef union _WHEA_ERROR_INJECTION_CAPABILITIES {
  struct {
    ULONG ProcessorCorrectable  :1;
    ULONG ProcessorUncorrectableNonFatal  :1;
    ULONG ProcessorUncorrectableFatal  :1;
    ULONG MemoryCorrectable  :1;
    ULONG MemoryUncorrectableNonFatal  :1;
    ULONG MemoryUncorrectableFatal  :1;
    ULONG PCIExpressCorrectable  :1;
    ULONG PCIExpressUncorrectableNonFatal  :1;
    ULONG PCIExpressUncorrectableFatal  :1;
    ULONG PlatformCorrectable  :1;
    ULONG PlatformUncorrectableNonFatal  :1;
    ULONG PlatformUncorrectableFatal  :1;
    ULONG IA64Corrected  :1;
    ULONG IA64Recoverable  :1;
    ULONG IA64Fatal  :1;
    ULONG IA64RecoverableCache  :1;
    ULONG IA64RecoverableRegFile  :1;
    ULONG Reserved  :15;
  };
  ULONG  AsULONG;
} WHEA_ERROR_INJECTION_CAPABILITIES, *PWHEA_ERROR_INJECTION_CAPABILITIES;
````


## -struct-fields

### -field ProcessorCorrectable

A single bit that indicates that a correctable processor error can be injected into the hardware platform.


### -field ProcessorUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal processor error can be injected into the hardware platform.


### -field ProcessorUncorrectableFatal

A single bit that indicates that an uncorrectable fatal processor error can be injected into the hardware platform.


### -field MemoryCorrectable

A single bit that indicates that a correctable memory error can be injected into the hardware platform.


### -field MemoryUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal memory error can be injected into the hardware platform.


### -field MemoryUncorrectableFatal

A single bit that indicates that an uncorrectable fatal memory error can be injected into the hardware platform.


### -field PCIExpressCorrectable

A single bit that indicates that a correctable PCI Express (PCIe) error can be injected into the hardware platform.


### -field PCIExpressUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal PCI Express (PCIe) error can be injected into the hardware platform.


### -field PCIExpressUncorrectableFatal

A single bit that indicates that an uncorrectable fatal PCI Express (PCIe) error can be injected into the hardware platform.


### -field PlatformCorrectable

A single bit that indicates that a correctable platform error can be injected into the hardware platform.


### -field PlatformUncorrectableNonFatal

A single bit that indicates that an uncorrectable nonfatal platform error can be injected into the hardware platform.


### -field PlatformUncorrectableFatal

A single bit that indicates that an uncorrectable fatal platform error can be injected into the hardware platform.


### -field IA64Corrected

A single bit that indicates that a corrected IA64 error can be injected into the hardware platform.


### -field IA64Recoverable

A single bit that indicates that a recoverable IA64 error can be injected into the hardware platform.


### -field IA64Fatal

A single bit that indicates that a fatal IA64 error can be injected into the hardware platform.


### -field IA64RecoverableCache

A single bit that indicates that a recoverable IA64 cache error can be injected into the hardware platform.


### -field IA64RecoverableRegFile

A single bit that indicates that a recoverable IA64 register file error can be injected into the hardware platform.


### -field Reserved

Reserved for system use.


### -field AsULONG

A ULONG representation of the contents of the WHEA_ERROR_INJECTION_CAPABILITIES union.


## -remarks
A user-mode WHEA management application calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559516">WHEAErrorInjectionMethods::GetErrorInjectionCapabilitiesRtn</a> method to retrieve a WHEA_ERROR_INJECTION_CAPABILITIES union that describes the types of hardware errors that can be injected into the hardware platform. If a PSHED plug-in is registered to participate in error injection, the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_get_injection_capabilities.md">GetInjectionCapabilities</a> callback function is called to provide this information back to the calling application. The application uses this information when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559518">WHEAErrorInjectionMethods::InjectErrorRtn</a> method to inject a hardware error into the hardware platform.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_get_injection_capabilities.md">GetInjectionCapabilities</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559516">WHEAErrorInjectionMethods::GetErrorInjectionCapabilitiesRtn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559518">WHEAErrorInjectionMethods::InjectErrorRtn</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_INJECTION_CAPABILITIES union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

