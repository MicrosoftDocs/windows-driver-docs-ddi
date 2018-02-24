---
UID: NF:ntddk.RtlConvertLongToLuid
title: RtlConvertLongToLuid function
author: windows-driver-content
description: The RtlConvertLongToLuid routine converts a long integer to a locally unique identifier (LUID), which is used by the system to represent a security privilege.
old-location: kernel\rtlconvertlongtoluid.htm
old-project: kernel
ms.assetid: bc03feaf-ee98-4b47-a659-809b5b8b9364
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/RtlConvertLongToLuid, k109_be3bfbe0-7a0b-43e3-a22e-2cd6e5a92f2e.xml, kernel.rtlconvertlongtoluid, RtlConvertLongToLuid routine [Kernel-Mode Driver Architecture], RtlConvertLongToLuid
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	RtlConvertLongToLuid
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# RtlConvertLongToLuid function


## -description


The <b>RtlConvertLongToLuid</b> routine converts a long integer to a locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>), which is used by the system to represent a security privilege.


## -syntax


````
LUID RtlConvertLongToLuid(
  _In_ LONG Long
);
````


## -parameters




### -param Long [in]

Specifies the long integer to convert. 


## -returns



<b>RtlConvertLongToLuid</b> returns the converted <a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>.




## -remarks



<b>RtlConvertLongToLuid</b> is used to convert a system-defined privilege value to the locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) used by the system to represent that privilege. Drivers typically pass a LUID to <b>SeSinglePrivilegeCheck</b>, which is usually called by network transport drivers.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561842">RtlEqualLuid</a>



<a href="..\ntddk\nf-ntddk-sesingleprivilegecheck.md">SeSinglePrivilegeCheck</a>



<a href="..\ntddk\nf-ntddk-rtlconvertulongtoluid.md">RtlConvertULongToLuid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561842">RtlEqualLuid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlConvertLongToLuid routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

