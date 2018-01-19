---
UID: NF:wdm.RtlCmEncodeMemIoResource
title: RtlCmEncodeMemIoResource function
author: windows-driver-content
description: The RtlCmEncodeMemIoResource routine updates a CM_PARTIAL_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses.
old-location: kernel\rtlcmencodememioresource.htm
old-project: kernel
ms.assetid: 69b978a2-3895-42fc-a87a-a97064d02e7a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlCmEncodeMemIoResource
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
req.alt-api: RtlCmEncodeMemIoResource
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlCmEncodeMemIoResource function



## -description
The <b>RtlCmEncodeMemIoResource</b> routine updates a <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to describe a range of memory or I/O port addresses.



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

A pointer to the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to update. 


### -param Type [in]

The resource type of the memory. This parameter can be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>.


### -param Length [in]

The length, in bytes, of the range of allocated addresses.


### -param Start [in]

The starting address of the range of memory or I/O port addresses.


## -returns
<b>RtlCmEncodeMemIoResource</b> returns an NTSTATUS value. This routine might return one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure has been updated.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The specified value for <i>Length</i> cannot be encoded in a <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One or more of the specified parameters are invalid.

 


## -remarks
Addresses that are larger than 32 bits in length must satisfy certain alignment restrictions or else the routine returns STATUS_UNSUCCESSFUL.

40 bits

Lowest 8 bits must be zero.

48 bits

Lowest 16 bits must be zero.

64 bits

Lowest 32 bits must be zero.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCmEncodeMemIoResource routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

