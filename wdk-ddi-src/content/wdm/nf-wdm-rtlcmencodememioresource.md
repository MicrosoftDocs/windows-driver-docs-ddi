---
UID: NF:wdm.RtlCmEncodeMemIoResource
title: RtlCmEncodeMemIoResource function
author: windows-driver-content
description: The RtlCmEncodeMemIoResource routine updates a CM_PARTIAL_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses.
old-location: kernel\rtlcmencodememioresource.htm
old-project: kernel
ms.assetid: 69b978a2-3895-42fc-a87a-a97064d02e7a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlCmEncodeMemIoResource, RtlCmEncodeMemIoResource routine [Kernel-Mode Driver Architecture], k109_62e5d339-a7ba-43ff-9886-bbae38b4957a.xml, kernel.rtlcmencodememioresource, wdm/RtlCmEncodeMemIoResource
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
-	RtlCmEncodeMemIoResource
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlCmEncodeMemIoResource function


## -description


The <b>RtlCmEncodeMemIoResource</b> routine updates a <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to describe a range of memory or I/O port addresses.


## -syntax


````
NTSTATUS RtlCmEncodeMemIoResource(
  _In_ PCM_PARTIAL_RESOURCE_DESCRIPTOR Descriptor,
  _In_ UCHAR                           Type,
  _In_ ULONGLONG                       Length,
  _In_ ULONGLONG                       Start
);
````


## -parameters




### -param Descriptor [in]

A pointer to the <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to update. 


### -param Type [in]

The resource type of the memory. This parameter can be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>.


### -param Length [in]

The length, in bytes, of the range of allocated addresses.


### -param Start [in]

The starting address of the range of memory or I/O port addresses.


## -returns



<b>RtlCmEncodeMemIoResource</b> returns an NTSTATUS value. This routine might return one of the following values:

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
The <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure has been updated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The specified value for <i>Length</i> cannot be encoded in a <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One or more of the specified parameters are invalid.

</td>
</tr>
</table>
 




## -remarks



Addresses that are larger than 32 bits in length must satisfy certain alignment restrictions or else the routine returns STATUS_UNSUCCESSFUL.

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

<a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCmEncodeMemIoResource routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

