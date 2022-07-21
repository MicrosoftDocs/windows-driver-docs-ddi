---
UID: NS:ntddk._KUSER_SHARED_DATA
tech.root: kernel
title: KUSER_SHARED_DATA (ntddk.h)
ms.date: 03/04/2022
targetos: Windows
description: This topic describes the KUSER_SHARED_DATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: KUSER_SHARED_DATA, *PKUSER_SHARED_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _KUSER_SHARED_DATA
 - PKUSER_SHARED_DATA
 - KUSER_SHARED_DATA
f1_keywords:
 - _KUSER_SHARED_DATA
 - ntddk/_KUSER_SHARED_DATA
 - PKUSER_SHARED_DATA
 - ntddk/PKUSER_SHARED_DATA
 - KUSER_SHARED_DATA
 - ntddk/KUSER_SHARED_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - _KUSER_SHARED_DATA
---

## -description

This topic describes the **KUSER_SHARED_DATA** structure.

## -struct-fields

### -field TickCountLowDeprecated

Current low 32-bit of tick count.

### -field TickCountMultiplier

Tick count multiplier.

### -field InterruptTime

Current 64-bit interrupt time in 100ns units.

### -field SystemTime

Current 64-bit system time in 100ns units.

### -field TimeZoneBias

Current 64-bit time zone bias.

### -field ImageNumberLow

Low image magic number for the host system.

### -field ImageNumberHigh

High image magic number for the host system.

### -field NtSystemRoot

Copy of system root in unicode. This field must be accessed via the **RtlGetNtSystemRoot** API for an accurate result.

### -field MaxStackTraceDepth

Maximum stack trace depth if tracing enabled.

### -field CryptoExponent

Crypto exponent value.

### -field TimeZoneId

Time zone ID.

### -field LargePageMinimum

Defines the **ULONG** member **LargePageMinimum**.

### -field AitSamplingValue

This value controls the AIT sampling rate.

### -field AppCompatFlag

This value controls switchback processing.

### -field RNGSeedVersion

Current kernel root RNG state seed version.

### -field GlobalValidationRunlevel

This value controls assertion failure handling.

### -field TimeZoneBiasStamp

Defines the **LONG** member **TimeZoneBiasStamp**.

### -field NtBuildNumber

The shared collective build number undecorated with C or F. **GetVersionEx** hides the real number.

### -field NtProductType

Product type. This field must be accessed via the **RtlGetNtProductType** API for an accurate result.

### -field ProductTypeIsValid

Defines the **BOOLEAN** member **ProductTypeIsValid**.

### -field Reserved0

Reserved for future use.

### -field NativeProcessorArchitecture

Defines the **USHORT** member **NativeProcessorArchitecture**.

### -field NtMajorVersion

The NT major version. Each process sees a version from its PEB, but if the process is running with an altered view of the system version, this field is used to correctly identify the version.

### -field NtMinorVersion

The NT minor version. Each process sees a version from its PEB, but if the process is running with an altered view of the system version, this field is used to correctly identify the version.

### -field ProcessorFeatures

Processor features.

### -field Reserved1

Reserved for future use.

### -field Reserved3

Reserved for future use.

### -field TimeSlip

Time slippage while in debugger.

### -field AlternativeArchitecture

Alternative system architecture. For example, NEC PC98xx on x86.

### -field BootId

Boot sequence, incremented for each boot attempt by the OS loader.

### -field SystemExpirationDate

If the system is an evaluation unit, the following field contains the date and time that the evaluation unit expires. A value of 0 indicates that there is no expiration. A non-zero value is the UTC absolute time that the system expires.

### -field SuiteMask

Suite support. This field must be accessed via the RtlGetSuiteMask API for an accurate result.

### -field KdDebuggerEnabled

TRUE if a kernel debugger is connected/enabled.

### -field MitigationPolicies

Mitigation policies.

### -field NXSupportPolicy

Defines the **UCHAR** member **NXSupportPolicy**.

### -field SEHValidationPolicy

Defines the **UCHAR** member **SEHValidationPolicy**.

### -field CurDirDevicesSkippedForDlls

Defines the **UCHAR** member **CurDirDevicesSkippedForDlls**.

### -field Reserved

Reserved for future use.

### -field CyclesPerYield

Measured duration of a single processor yield, in cycles. This is used by lock packages to determine how many times to spin waiting for a state change before blocking.

### -field ActiveConsoleId

Current console session Id. Always zero on non-TS systems. This field must be accessed via the **RtlGetActiveConsoleId** API for an accurate result.

### -field DismountCount

Force-dismounts cause handles to become invalid. Rather than always probe handles, a serial number of dismounts is maintained that clients can use to see if they need to probe handles.

### -field ComPlusPackage

This field indicates the status of the 64-bit COM+ package on the system. It indicates whether the Intermediate Language (IL) COM+ images need to use the 64-bit COM+ runtime or the 32-bit COM+ runtime.

### -field LastSystemRITEventTickCount

Time in tick count for system-wide last user input across all terminal sessions. For MP performance, it is not updated all the time (for example, once a minute per session). It is used for idle detection.

### -field NumberOfPhysicalPages

Number of physical pages in the system. This can dynamically change as physical memory can be added or removed from a running system.

### -field SafeBootMode

True if the system was booted in safe boot mode.

### -field VirtualizationFlags

Virtualization flags.

### -field ArchStartedInEl2

Keep this bitfield in sync with the one in arc.w.

### -field QcSlIsSupported

Keep this bitfield in sync with the one in arc.w.

### -field Reserved12

Reserved for future use.

### -field DUMMYUNIONNAME2

This is a packed bitfield that contains various flags concerning the system state. They must be manipulated using interlocked operations. **DbgMultiSessionSku** must be accessed via the **RtlIsMultiSessionSku** API for an accurate result.

### -field DUMMYUNIONNAME2.SharedDataFlags

Defines the **ULONG** member **SharedDataFlags**.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2

Defines the **DUMMYSTRUCTNAME2** structure.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgErrorPortPresent

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgElevationEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgVirtEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgInstallerDetectEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgLkgEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgDynProcessorEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgConsoleBrokerEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgSecureBootEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgMultiSessionSku

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgMultiUsersInSessionSku

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.DbgStateSeparationEnabled

For debugger only. Do not use. Use the bit definitions instead.

### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME2.SpareBits

For the debugger only. Do not use. Use the bit definitions instead.

### -field DataFlagsPad

Defines the **ULONG** member **DataFlagsPad**.

### -field TestRetInstruction

Depending on the processor, the code for fast system call will differ. This field is only used on 32-bit systems.

### -field QpcFrequency

Defines the **LONGLONG** member **QpcFrequency**.

### -field SystemCall

On AMD64, this value is initialized to a nonzero value if the system operates with an altered view of the system service call mechanism.

### -field Reserved2

Reserved for future use.

### -field SystemCallPad

Reserved for future use.

### -field DUMMYUNIONNAME3

The 64-bit tick count.

### -field DUMMYUNIONNAME3.TickCount

Defines the **KSYSTEM_TIME** member **TickCount**.

### -field DUMMYUNIONNAME3.TickCountQuad

Defines the **ULONG64** member **TickCountQuad**.

### -field DUMMYUNIONNAME3.DUMMYSTRUCTNAME

Defines **DUMMYSTRUCTNAME**.

### -field DUMMYUNIONNAME3.DUMMYSTRUCTNAME.ReservedTickCountOverlay

Defines the **ULONG** member **ReservedTickCountOverlay**.

### -field DUMMYUNIONNAME3.DUMMYSTRUCTNAME.TickCountPad

Defines the **ULONG** member **TickCountPad**.

### -field Cookie

Cookie for encoding pointers system wide.

### -field CookiePad

Reserved for future use.

### -field ConsoleSessionForegroundProcessId

Client id of the process having the focus in the current active console session id. This field must be accessed via the **RtlGetConsoleSessionForegroundProcessId** API for an accurate result.

### -field TimeUpdateLock

Placeholder for the (internal) time update lock. This data is used to implement the precise time services. It is aligned on a 64-byte cache-line boundary and arranged in the order of typical accesses.

### -field BaselineSystemTimeQpc

The performance counter value used to establish the current system time.

### -field BaselineInterruptTimeQpc

The performance counter value used to compute the last interrupt time.

### -field QpcSystemTimeIncrement

The scaled number of system time seconds represented by a single performance count (this value may vary to achieve time synchronization).

### -field QpcInterruptTimeIncrement

The scaled number of interrupt time seconds represented by a single performance count (this value is constant after the system is booted).

### -field QpcSystemTimeIncrementShift

The scaling shift count applied to the performance counter system time increment.

### -field QpcInterruptTimeIncrementShift

The scaling shift count applied to the performance counter interrupt time increment.

### -field UnparkedProcessorCount

The count of unparked processors.

### -field EnclaveFeatureMask

A bitmask of enclave features supported on this system. This field must be accessed via the **RtlIsEnclareFeaturePresent** API for an accurate result.

### -field TelemetryCoverageRound

Current coverage round for telemetry based coverage.

### -field UserModeGlobalLogger

The following field is used for ETW user mode global logging (UMGL).

### -field ImageFileExecutionOptions

Settings that can enable the use of Image File Execution Options from HKCU in addition to the original HKLM.

### -field LangGenerationCount

Generation of the kernel structure holding system language information.

### -field Reserved4

Reserved for future use.

### -field InterruptTimeBias

Current 64-bit interrupt time bias in 100ns units.

### -field QpcBias

Current 64-bit performance counter bias, in performance counter units before the shift is applied.

### -field ActiveProcessorCount

Number of active processors.

### -field ActiveGroupCount

Number of active groups.

### -field Reserved9

Reserved for future use.

### -field QpcData

Defines the **USHORT** member QpcData.

### -field QpcBypassEnabled

A boolean indicating whether performance counter queries can read the counter directly (bypassing the system call).

### -field QpcShift

Shift applied to the raw counter value to derive the QPC count.

### -field TimeZoneBiasEffectiveStart

Defines the **LARGE_INTEGER** member **TimeZoneBiasEffectiveStart**.

### -field TimeZoneBiasEffectiveEnd

Defines the **LARGE_INTEGER** member **TimeZoneBiasEffectiveEnd**.

### -field XState

Extended processor state configuration.

### -field FeatureConfigurationChangeStamp

Defines the **KSYSTEM_TIME** member **FeatureConfigurationChangeStamp**.

### -field Spare

Defines the **ULONG** member **Spare**.

### -field UserPointerAuthMask

Defines the **ULONG64** member **UserPointerAuthMask**.

## -remarks

## -see-also
