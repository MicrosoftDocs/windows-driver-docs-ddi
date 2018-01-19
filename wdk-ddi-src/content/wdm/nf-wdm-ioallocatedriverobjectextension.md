---
UID: NF:wdm.IoAllocateDriverObjectExtension
title: IoAllocateDriverObjectExtension function
author: windows-driver-content
description: The IoAllocateDriverObjectExtension routine allocates a per-driver context area, called a driver object extension, and assigns a unique identifier to it.
old-location: kernel\ioallocatedriverobjectextension.htm
old-project: kernel
ms.assetid: e4e4e721-5b5c-48e8-99cb-d04c6b0eb807
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoAllocateDriverObjectExtension
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoAllocateDriverObjectExtension
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
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoAllocateDriverObjectExtension function



## -description
The <b>IoAllocateDriverObjectExtension</b> routine allocates a per-driver context area, called a <a href="wdkgloss.d#wdkgloss.driver_object_extension#wdkgloss.driver_object_extension"><i>driver object extension</i></a>, and assigns a unique identifier to it.



## -syntax

````
NTSTATUS IoAllocateDriverObjectExtension(
  _In_  PDRIVER_OBJECT DriverObject,
  _In_  PVOID          ClientIdentificationAddress,
  _In_  ULONG          DriverObjectExtensionSize,
  _Out_ PVOID          *DriverObjectExtension
);
````


## -parameters

### -param DriverObject [in]

Pointer to a driver object to which the context area will be associated.


### -param ClientIdentificationAddress [in]

Specifies a unique identifier for the context area to be allocated.


### -param DriverObjectExtensionSize [in]

Specifies the length, in bytes, of the context area to be allocated.


### -param DriverObjectExtension [out]

Pointer to, on completion, the allocated context area. 


## -returns
<b>IoAllocateDriverObjectExtension</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Indicates that the routine allocated an extension of the requested size.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Indicates that the memory could not be allocated for the driver object extension.
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>Indicates that a driver object extension with the given <i>ClientIdentificationAddress</i> already exists. 

 


## -remarks
Memory allocated by the system for the driver object extension is resident storage and is accessible from any IRQL. The allocated storage is automatically freed by the I/O manager when the driver object is deleted.

Callers of this routine must provide a unique identifier for <i>ClientIdentificationAddress</i>. To retrieve a pointer to the context area, a caller passes the <i>ClientIdentificationAddress</i> to <a href="..\wdm\nf-wdm-iogetdriverobjectextension.md">IoGetDriverObjectExtension</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iogetdriverobjectextension.md">IoGetDriverObjectExtension</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAllocateDriverObjectExtension routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

