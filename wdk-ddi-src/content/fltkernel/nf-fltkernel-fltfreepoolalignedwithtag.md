---
UID: NF:fltkernel.FltFreePoolAlignedWithTag
title: FltFreePoolAlignedWithTag function
author: windows-driver-content
description: The FltFreePoolAlignedWithTag routine frees a cache-aligned buffer that was allocated by a previous call to FltAllocatePoolAlignedWithTag.
old-location: ifsk\fltfreepoolalignedwithtag.htm
old-project: ifsk
ms.assetid: 295a34e4-734e-41ba-bf2e-378333c14e2c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltFreePoolAlignedWithTag routine [Installable File System Drivers], FltApiRef_e_to_o_dc83e564-1331-48f0-ad7e-8cdeaa677952.xml, ifsk.fltfreepoolalignedwithtag, FltFreePoolAlignedWithTag, fltkernel/FltFreePoolAlignedWithTag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltFreePoolAlignedWithTag
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFreePoolAlignedWithTag function


## -description


The <b>FltFreePoolAlignedWithTag</b> routine frees a cache-aligned buffer that was allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>. 


## -syntax


````
VOID FltFreePoolAlignedWithTag(
  _In_ PFLT_INSTANCE Instance,
  _In_ PVOID         Buffer,
  _In_ ULONG         Tag
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for a caller-owned minifilter driver instance that is attached to the volume. Must be the same instance pointer as the one used in the call to <a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>. 


### -param Buffer [in]

Address of the block of pool memory to be freed. 


### -param Tag [in]

Tag used to mark the pool block. Must be the same tag as the one used in the call to <a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>. 


## -returns



None




## -remarks



The memory that the <i>Buffer</i> parameter points to must not be accessed after it is freed by <b>FltFreePoolAlignedWithTag</b>. 

The caller of <b>FltFreePoolAlignedWithTag</b> can be running at IRQL DISPATCH_LEVEL if a <b>NonPaged</b><i>XxxPoolType</i> value was specified when the memory was allocated. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFreePoolAlignedWithTag routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

