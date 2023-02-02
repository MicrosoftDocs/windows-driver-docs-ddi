---
UID: NF:ntddk.RtlGetEnabledExtendedFeatures
title: RtlGetEnabledExtendedFeatures function (ntddk.h)
description: The RtlGetEnabledExtendedFeatures routine returns a mask of extended processor features that are enabled by the system.
old-location: kernel\rtlgetenabledextendedfeatures.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlGetEnabledExtendedFeatures function"]
ms.keywords: RtlGetEnabledExtendedFeatures, RtlGetEnabledExtendedFeatures routine [Kernel-Mode Driver Architecture], XSTATE_MASK_GSSE, XSTATE_MASK_LEGACY, XSTATE_MASK_LEGACY_FLOATING_POINT, XSTATE_MASK_LEGACY_SSE, k109_94843b2d-9abe-4b82-a781-dd2863ddc9c1.xml, kernel.rtlgetenabledextendedfeatures, wdm/RtlGetEnabledExtendedFeatures
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
req.lib: Ntdll.lib (user mode); NtosKrnl.lib (kernel mode); OneCoreUAP.lib on Windows 10
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlGetEnabledExtendedFeatures
 - ntddk/RtlGetEnabledExtendedFeatures
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
 - API-MS-Win-Core-XState-l1-1-0.dll
 - API-MS-Win-Core-XState-l1-1-1.dll
 - API-MS-Win-Core-XState-L1-1-2.dll
api_name:
 - RtlGetEnabledExtendedFeatures
---

# RtlGetEnabledExtendedFeatures function


## -description

The <b>RtlGetEnabledExtendedFeatures</b> routine returns a mask of extended processor features that are enabled by the system.

## -parameters

### -param FeatureMask [in]


A 64-bit feature mask. This parameter indicates a set of extended processor features for which the caller requests information about whether the features are enabled. If a mask bit is one, the caller requests information about the feature that corresponds to this mask bit. The caller sets all other mask bits to zero. Set this parameter to (ULONG64)(-1) to get the mask of all enabled features. To determine whether a particular set of features is enabled, set this parameter to the bitwise OR of one or more <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesaveextendedprocessorstate">XSTATE_MASK_XXX</a> flag bits.

## -returns

<b>RtlGetEnabledExtendedFeatures</b> returns a 64-bitmask of enabled extended processor features. The routine calculates this mask as the intersection (bitwise AND) between all enabled features and the value of the <i>FeatureMask</i> parameter. For more information about the features that are indicated by this return value, see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesaveextendedprocessorstate">XSTATE_MASK_XXX</a>.

<b>RtlGetEnabledExtendedFeatures</b> returns 0 if the XSAVE and XRSTOR instructions are disabled by the system.  This happens even if the system supports XSTATE_MASK_LEGACY_FLOATING_POINT and XSTATE_MASK_LEGACY_SSE features. Use <b>ExIsProcessorFeaturePresent </b>or CPUID to determine the availability of x87, MMX, and SSE processor features on x86 or x64 systems.

## -remarks

Another routine, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisprocessorfeaturepresent">ExIsProcessorFeaturePresent</a>, indicates whether an extended processor feature is available. Unlike <b>RtlGetEnabledExtendedFeatures</b>, however, it does not indicate whether the operating system has enabled the feature for use by kernel-mode drivers.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisprocessorfeaturepresent">ExIsProcessorFeaturePresent</a>
