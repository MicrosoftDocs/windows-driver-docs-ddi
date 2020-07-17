---
UID: NF:ntddk.RtlConvertUlongToLuid
title: RtlConvertUlongToLuid function (ntddk.h)
description: The RtlConvertUlongToLuid routine converts an unsigned long integer to a locally unique identifier (LUID), which is used by the system to represent a security privilege.
old-location: kernel\rtlconvertulongtoluid.htm
tech.root: kernel
ms.assetid: f3c1e2d5-8bb8-486c-a78a-3ddde6ab64bd
ms.date: 04/30/2018
keywords: ["RtlConvertUlongToLuid function"]
ms.keywords: RtlConvertUlongToLuid, RtlConvertUlongToLuid routine [Kernel-Mode Driver Architecture], k109_25b3458f-dc47-436f-af5b-7d6a9d8eeb2a.xml, kernel.rtlconvertulongtoluid, ntddk/RtlConvertUlongToLuid
f1_keywords:
 - "ntddk/RtlConvertUlongToLuid"
 - "RtlConvertUlongToLuid"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- RtlConvertUlongToLuid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlConvertUlongToLuid function


## -description


The <b>RtlConvertUlongToLuid</b> routine converts an unsigned long integer to a locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>), which is used by the system to represent a security privilege.


## -parameters




### -param Ulong [in]

Specifies the unsigned long integer to convert. 


## -returns



<b>RtlConvertUlongToLuid</b> returns the converted <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>.




## -remarks



<b>RtlConvertUlongToLuid</b> is used to convert a system-defined privilege value, passed as a ULONG, to a locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) used by the system to represent that privilege. Drivers typically pass a LUID to <b>SeSinglePrivilegeCheck</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlconvertlongtoluid">RtlConvertLongToLuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">RtlEqualLuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-sesingleprivilegecheck">SeSinglePrivilegeCheck</a>
 

 

