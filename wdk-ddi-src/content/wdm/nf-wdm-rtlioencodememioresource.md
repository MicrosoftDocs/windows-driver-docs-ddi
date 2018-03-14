---
UID: NF:wdm.RtlIoEncodeMemIoResource
title: RtlIoEncodeMemIoResource function
author: windows-driver-content
description: The RtlIoEncodeMemIoResource routine updates an IO_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses.
old-location: kernel\rtlioencodememioresource.htm
old-project: kernel
ms.assetid: b2f51d54-3fda-4cbf-a148-0572122ed9fa
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlIoEncodeMemIoResource, RtlIoEncodeMemIoResource routine [Kernel-Mode Driver Architecture], k109_2e51e72a-98c4-4600-8e9c-41251c3e9849.xml, kernel.rtlioencodememioresource, wdm/RtlIoEncodeMemIoResource
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlIoEncodeMemIoResource
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlIoEncodeMemIoResource function


## -description


The <b>RtlIoEncodeMemIoResource</b> routine updates an <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure to describe a range of memory or I/O port addresses.


## -syntax


````
NTSTATUS RtlIoEncodeMemIoResource(
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor,
  _In_ UCHAR                   Type,
  _In_ ULONGLONG               Length,
  _In_ ULONGLONG               Alignment,
  _In_ ULONGLONG               MinimumAddress,
  _In_ ULONGLONG               MaximumAddress
);
````


## -parameters




### -param Descriptor [in]

A pointer to the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure to update.


### -param Type [in]

The resource type of the address range. This parameter can be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>. 


### -param Length [in]

The length, in bytes, of the range of assignable addresses. 


### -param Alignment [in]

The alignment, in bytes, of the starting address of address range.


### -param MinimumAddress [in]

The minimum address that can be assigned to the device. 


### -param MaximumAddress [in]

The maximum address that can be assigned to the device.


## -returns



<b>RtlIoEncodeMemIoResource</b> returns an NTSTATUS value. This routine might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure was updated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The specified value for <i>Length</i> or <i>Alignment</i> could not be encoded in an <b>IO_RESOURCE_DESCRIPTOR</b> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One or more of the specified parameters were invalid.

</td>
</tr>
</table>
 




## -remarks



Addresses that are larger than 32 bits in length must satisfy certain alignment restrictions, or else the routine returns STATUS_UNSUCCESSFUL.

<table>
<tr>
<th>Address length</th>
<th>Alignment restriction</th>
</tr>
<tr>
<td>
40 bits

</td>
<td>
Lowest 8 bits must be zero.

</td>
</tr>
<tr>
<td>
48 bits

</td>
<td>
Lowest 16 bits must be zero.

</td>
</tr>
<tr>
<td>
64 bits

</td>
<td>
Lowest 32 bits must be zero.

</td>
</tr>
</table>
 




## -see-also

<a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a>



<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



 

 


