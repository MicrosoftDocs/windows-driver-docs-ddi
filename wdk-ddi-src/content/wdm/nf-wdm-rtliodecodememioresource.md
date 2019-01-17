---
UID: NF:wdm.RtlIoDecodeMemIoResource
title: RtlIoDecodeMemIoResource function
description: The RtlIoDecodeMemIoResource routine provides the address information that is contained in an IO_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses.
old-location: kernel\rtliodecodememioresource.htm
tech.root: kernel
ms.assetid: a6bdbd68-b4ec-467f-9892-e968243e8994
ms.date: 04/30/2018
ms.keywords: RtlIoDecodeMemIoResource, RtlIoDecodeMemIoResource routine [Kernel-Mode Driver Architecture], k109_27e29ad7-3e41-44ad-b3da-027180f51d2a.xml, kernel.rtliodecodememioresource, wdm/RtlIoDecodeMemIoResource
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlIoDecodeMemIoResource
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIoDecodeMemIoResource function


## -description


The <b>RtlIoDecodeMemIoResource</b> routine provides the address information that is contained in an <a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a> structure that describes a range of memory or I/O port addresses.


## -parameters




### -param Descriptor [in]

A pointer to the <a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a> structure to provide the address information for.


### -param Alignment [out, optional]

A pointer to a variable that receives the alignment, in bytes, of the address range. This parameter can be <b>NULL</b>. 


### -param MinimumAddress [out, optional]

A pointer to a variable that receives the minimum address of the address range. This parameter can be <b>NULL</b>.


### -param MaximumAddress [out, optional]

A pointer to a variable that receives the maximum address of the address range. This parameter can be <b>NULL</b>.


## -returns



<b>RtlIoDecodeMemIoResource</b> returns the length of the address range, in bytes.




## -remarks



The <b>Type</b> member of the <a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a> structure must be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>. 




## -see-also




<a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561952">RtlIoEncodeMemIoResource</a>
 

 

