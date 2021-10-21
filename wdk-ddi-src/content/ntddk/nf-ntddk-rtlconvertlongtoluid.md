---
UID: NF:ntddk.RtlConvertLongToLuid
title: RtlConvertLongToLuid function (ntddk.h)
description: The RtlConvertLongToLuid routine converts a long integer to a locally unique identifier (LUID), which is used by the system to represent a security privilege.
old-location: kernel\rtlconvertlongtoluid.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlConvertLongToLuid function"]
ms.keywords: RtlConvertLongToLuid, RtlConvertLongToLuid routine [Kernel-Mode Driver Architecture], k109_be3bfbe0-7a0b-43e3-a22e-2cd6e5a92f2e.xml, kernel.rtlconvertlongtoluid, ntddk/RtlConvertLongToLuid
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlConvertLongToLuid
 - ntddk/RtlConvertLongToLuid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - RtlConvertLongToLuid
---

# RtlConvertLongToLuid function


## -description

The <b>RtlConvertLongToLuid</b> routine converts a long integer to a locally unique identifier (<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>), which is used by the system to represent a security privilege.

## -parameters

### -param Long 

[in]
Specifies the long integer to convert.

## -returns

<b>RtlConvertLongToLuid</b> returns the converted <a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>.

## -remarks

<b>RtlConvertLongToLuid</b> is used to convert a system-defined privilege value to the locally unique identifier (<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) used by the system to represent that privilege. Drivers typically pass a LUID to <b>SeSinglePrivilegeCheck</b>, which is usually called by network transport drivers.

## -see-also

<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlconvertulongtoluid">RtlConvertULongToLuid</a>



[RtlEqualLuid](../wdm/nf-wdm-rtlequalluid.md)



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-sesingleprivilegecheck">SeSinglePrivilegeCheck</a>