---
UID: NF:wdm.ClfsDeleteMarshallingArea
title: ClfsDeleteMarshallingArea function
author: windows-driver-content
description: The ClfsDeleteMarshallingArea routine deletes a marshalling area.
old-location: kernel\clfsdeletemarshallingarea.htm
old-project: kernel
ms.assetid: 8aa7aec3-85d7-40a2-a63d-bee8c5ce1ff9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsDeleteMarshallingArea
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsDeleteMarshallingArea
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsDeleteMarshallingArea function



## -description
The <b>ClfsDeleteMarshallingArea</b> routine deletes a marshalling area.



## -syntax

````
NTSTATUS ClfsDeleteMarshallingArea(
  _In_ PVOID pvMarshalContext
);
````


## -parameters

### -param pvMarshalContext [in]

A pointer to an opaque context that represents a marshalling area. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>.


## -returns
<b>ClfsDeleteMarshallingArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
Before deleting the marshalling area, <b>ClfsDeleteMarshallingArea</b> flushes all of the log I/O blocks associated with the marshalling area.

The marshalling area goes away only after all references to it go away. For example, the marshalling area remains in memory if it still has an open read context.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsDeleteMarshallingArea routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

