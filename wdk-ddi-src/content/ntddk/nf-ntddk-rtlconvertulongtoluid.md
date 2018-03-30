---
UID: NF:ntddk.RtlConvertUlongToLuid
title: RtlConvertUlongToLuid function
author: windows-driver-content
description: The RtlConvertUlongToLuid routine converts an unsigned long integer to a locally unique identifier (LUID), which is used by the system to represent a security privilege.
old-location: kernel\rtlconvertulongtoluid.htm
old-project: kernel
ms.assetid: f3c1e2d5-8bb8-486c-a78a-3ddde6ab64bd
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlConvertUlongToLuid, RtlConvertUlongToLuid routine [Kernel-Mode Driver Architecture], k109_25b3458f-dc47-436f-af5b-7d6a9d8eeb2a.xml, kernel.rtlconvertulongtoluid, ntddk/RtlConvertUlongToLuid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	RtlConvertUlongToLuid
product: Windows
targetos: Windows
req.typenames: SUBSYSTEM_INFORMATION_TYPE, *PSUBSYSTEM_INFORMATION_TYPE
---

# RtlConvertUlongToLuid function


## -description


The <b>RtlConvertUlongToLuid</b> routine converts an unsigned long integer to a locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>), which is used by the system to represent a security privilege.


## -parameters




### -param Ulong [in]

Specifies the unsigned long integer to convert. 


## -returns



<b>RtlConvertUlongToLuid</b> returns the converted <a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>.




## -remarks



<b>RtlConvertUlongToLuid</b> is used to convert a system-defined privilege value, passed as a ULONG, to a locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) used by the system to represent that privilege. Drivers typically pass a LUID to <b>SeSinglePrivilegeCheck</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561790">RtlConvertLongToLuid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561842">RtlEqualLuid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563740">SeSinglePrivilegeCheck</a>
 

 

