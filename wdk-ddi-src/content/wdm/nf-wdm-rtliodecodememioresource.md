---
UID: NF:wdm.RtlIoDecodeMemIoResource
title: RtlIoDecodeMemIoResource function
author: windows-driver-content
description: The RtlIoDecodeMemIoResource routine provides the address information that is contained in an IO_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses.
old-location: kernel\rtliodecodememioresource.htm
old-project: kernel
ms.assetid: a6bdbd68-b4ec-467f-9892-e968243e8994
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIoDecodeMemIoResource routine [Kernel-Mode Driver Architecture], wdm/RtlIoDecodeMemIoResource, kernel.rtliodecodememioresource, RtlIoDecodeMemIoResource, k109_27e29ad7-3e41-44ad-b3da-027180f51d2a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	RtlIoDecodeMemIoResource
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlIoDecodeMemIoResource function


## -description


The <b>RtlIoDecodeMemIoResource</b> routine provides the address information that is contained in an <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that describes a range of memory or I/O port addresses.


## -syntax


````
ULONGLONG RtlIoDecodeMemIoResource(
  _In_      PIO_RESOURCE_DESCRIPTOR Descriptor,
  _Out_opt_ PULONGLONG              Alignment,
  _Out_opt_ PULONGLONG              MinimumAddress,
  _Out_opt_ PULONGLONG              MaximumAddress
);
````


## -parameters




### -param Descriptor [in]

A pointer to the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure to provide the address information for.


### -param Alignment [out, optional]

A pointer to a variable that receives the alignment, in bytes, of the address range. This parameter can be <b>NULL</b>. 


### -param MinimumAddress [out, optional]

A pointer to a variable that receives the minimum address of the address range. This parameter can be <b>NULL</b>.


### -param MaximumAddress [out, optional]

A pointer to a variable that receives the maximum address of the address range. This parameter can be <b>NULL</b>.


## -returns


<b>RtlIoDecodeMemIoResource</b> returns the length of the address range, in bytes.



## -remarks


The <b>Type</b> member of the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure must be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>. 



## -see-also

<a href="..\wdm\nf-wdm-rtlioencodememioresource.md">RtlIoEncodeMemIoResource</a>

<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIoDecodeMemIoResource routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

