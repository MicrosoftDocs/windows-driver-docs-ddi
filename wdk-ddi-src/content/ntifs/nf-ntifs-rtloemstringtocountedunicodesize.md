---
UID: NF:ntifs.RtlOemStringToCountedUnicodeSize
title: RtlOemStringToCountedUnicodeSize macro
author: windows-driver-content
description: The RtlOemStringToCountedUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a counted Unicode string.
old-location: ifsk\rtloemstringtocountedunicodesize.htm
old-project: ifsk
ms.assetid: a618420f-ea69-471d-82a0-1e86f85e270b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlOemStringToCountedUnicodeSize, RtlOemStringToCountedUnicodeSize routine [Installable File System Drivers], ifsk.rtloemstringtocountedunicodesize, ntifs/RtlOemStringToCountedUnicodeSize, rtlref_dc10fcb6-356a-4c09-aea6-c386030039f0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	RtlOemStringToCountedUnicodeSize
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlOemStringToCountedUnicodeSize macro


## -description


The <b>RtlOemStringToCountedUnicodeSize</b> routine determines the size, in bytes, that a given OEM string will be after it is translated into a counted Unicode string. 


## -parameters




### -param STRING

TBD






#### - OemString [in]

Pointer to a caller-allocated OEM string. 


## -remarks



<b>RtlOemStringToCountedUnicodeSize</b> can be called to determine how much memory to allocate when translating an OEM string to Unicode with <b>RtlOemStringToCountedUnicodeString</b>. The returned value does not include space for a NULL terminator for the Unicode string.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553142">RtlOemStringToCountedUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553147">RtlOemStringToUnicodeSize</a>
 

 

