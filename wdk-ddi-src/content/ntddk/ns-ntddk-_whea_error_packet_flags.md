---
UID: NS:ntddk._WHEA_ERROR_PACKET_FLAGS
title: WHEA_ERROR_PACKET_FLAGS (ntddk.h)
description: The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a WHEA_ERROR_PACKET structure.
tech.root: whea
ms.date: 12/08/2022
keywords: ["WHEA_ERROR_PACKET_FLAGS structure"]
ms.keywords: "*PWHEA_ERROR_PACKET_FLAGS, PWHEA_ERROR_PACKET_FLAGS, PWHEA_ERROR_PACKET_FLAGS union pointer [WHEA Drivers and Applications], WHEA_ERROR_PACKET_FLAGS, WHEA_ERROR_PACKET_FLAGS union [WHEA Drivers and Applications], _WHEA_ERROR_PACKET_FLAGS, ntddk/PWHEA_ERROR_PACKET_FLAGS, ntddk/WHEA_ERROR_PACKET_FLAGS, whea.whea_error_packet_flags, whearef_c193e4e7-f233-4de0-93ac-5e7b841a6c6e.xml"
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
req.irql: 
targetos: Windows
req.typenames: WHEA_ERROR_PACKET_FLAGS, *PWHEA_ERROR_PACKET_FLAGS
f1_keywords:
 - _WHEA_ERROR_PACKET_FLAGS
 - ntddk/_WHEA_ERROR_PACKET_FLAGS
 - PWHEA_ERROR_PACKET_FLAGS
 - ntddk/PWHEA_ERROR_PACKET_FLAGS
 - WHEA_ERROR_PACKET_FLAGS
 - ntddk/WHEA_ERROR_PACKET_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_PACKET_FLAGS
 - PWHEA_ERROR_PACKET_FLAGS
 - WHEA_ERROR_PACKET_FLAGS
---

## -description

The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a [WHEA_ERROR_PACKET](/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)) structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.PreviousError

A single bit that indicates whether the hardware error packet contains information about a fatal hardware error. This error caused the operating system to generate a bug check and restart.

### -field DUMMYSTRUCTNAME.CriticalEvent

### -field DUMMYSTRUCTNAME.HypervisorError

A single bit that indicates that a hypervisor error has occurred.

### -field DUMMYSTRUCTNAME.Simulated

A single bit that indicates that the error condition was simulated.

### -field DUMMYSTRUCTNAME.PlatformPfaControl

A single bit that indicates whether WHEA or a PSHED plug-in is in control of predictive failure analysis (PFA). If this bit is set, the PSHED plug-in is in control of PFA and must set the **PlatformDirectedOffline** to bring an [ECC](/windows-hardware/drivers/) memory page into an offline state.

For more information about PFA support for WHEA, see [Predictive Failure Analysis (PFA)](/windows-hardware/drivers/whea/predictive-failure-analysis--pfa-).

### -field DUMMYSTRUCTNAME.PlatformDirectedOffline

A single bit that indicates whether the PSHED plug-in that performs PFA on a system component has determined if the component should be brought into an offline state. This bit is only valid if the **PlatformPfaControl** member is set.

### -field DUMMYSTRUCTNAME.AddressTranslationRequired

This field indicates that WHEA has identified this packet represents a memory error but the error data gathered by WHEA does not contain
a valid physical address. A PSHED Plug-in may perform platform specific translation on the address to allow WHEA to take action. If
this flag is set and the **RecoveryOptional** flag is 0 the system crashes with [bug check code 0x124](/windows-hardware/drivers/debugger/bug-check-0x124---whea-uncorrectable-error) indicating a fatal hardware error.

### -field DUMMYSTRUCTNAME.AddressTranslationCompleted

If the **AddressTranslationRequired** bit is set, a PSHED plug-in may set this bit during its retrieve error info callback to indicate the
memory address contained in the error state has been updated to reflect a valid physical address. This will allow WHEA to perform
recovery.

### -field DUMMYSTRUCTNAME.RecoveryOptional

This field indicates that recovery is optional and the system may continue execution without further action. This flag is set
for errors where action is optional and AddressTranslationRequired is set to prevent the system from crashing if a PSHED plug-in
does not provide a translation.

### -field DUMMYSTRUCTNAME.Reserved2

Reserved for system use.

### -field AsULONG

A ULONG representation of the contents of the **WHEA_ERROR_PACKET_FLAGS** union.

## -remarks

The WHEA_ERROR_PACKET_FLAGS union describes the error condition reported by using a [**WHEA_ERROR_PACKET**](/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)) structure.

## -see-also

[Predictive Failure Analysis (PFA)](/windows-hardware/drivers/whea/predictive-failure-analysis--pfa-)

[**WHEA_ERROR_PACKET**](/previous-versions/windows/hardware/drivers/ff560465(v=vs.85))
