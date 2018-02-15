---
UID: NE:wdm._IO_PRIORITY_HINT
title: "_IO_PRIORITY_HINT"
author: windows-driver-content
description: The IO_PRIORITY_HINT enumeration type specifies the priority hint for an IRP.
old-location: kernel\io_priority_hint.htm
old-project: kernel
ms.assetid: 38d19398-b34f-4934-b643-df119ebd9711
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MaxIoPriorityTypes, IoPriorityCritical, IO_PRIORITY_HINT, wdm/IoPriorityVeryLow, wdm/IoPriorityLow, _IO_PRIORITY_HINT, wdm/MaxIoPriorityTypes, IO_PRIORITY_HINT enumeration [Kernel-Mode Driver Architecture], IoPriorityVeryLow, wdm/IoPriorityNormal, wdm/IoPriorityCritical, wdm/IoPriorityHigh, sysenum_0b8187d9-c762-45d2-a310-294c3c696608.xml, IoPriorityLow, wdm/IO_PRIORITY_HINT, kernel.io_priority_hint, IoPriorityHigh, IoPriorityNormal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	IO_PRIORITY_HINT
product: Windows
targetos: Windows
req.typenames: IO_PRIORITY_HINT
req.product: Windows 10 or later.
---

# _IO_PRIORITY_HINT enumeration


## -description


The <b>IO_PRIORITY_HINT</b> enumeration type specifies the <a href="https://msdn.microsoft.com/c34afff2-32f2-451b-ab16-ff048d5c3204">priority hint</a> for an IRP.


## -syntax


````
typedef enum _IO_PRIORITY_HINT { 
  IoPriorityVeryLow   = 0,
  IoPriorityLow       = 1,
  IoPriorityNormal    = 2,
  IoPriorityHigh      = 3,
  IoPriorityCritical  = 4,
  MaxIoPriorityTypes  = 5
} IO_PRIORITY_HINT;
````


## -enum-fields




### -field IoPriorityVeryLow

Specifies the lowest possible priority hint level. The system uses this value for background I/O operations.


### -field IoPriorityLow

Specifies a low-priority hint level. 


### -field IoPriorityNormal

Specifies a normal-priority hint level. This value is the default setting for an IRP.


### -field IoPriorityHigh

Specifies a high-priority hint level. This value is reserved for use by the system.


### -field IoPriorityCritical

Specifies the highest-priority hint level. This value is reserved for use by the system.


### -field MaxIoPriorityTypes

Marks the limit for priority hints. Any priority hint value must be less than <b>MaxIoPriorityTypes</b>.


## -remarks



For more information about priority hints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565403">Using IRP Priority Hints</a>.




## -see-also

<a href="..\wdm\nf-wdm-iosetiopriorityhint.md">IoSetIoPriorityHint</a>



<a href="..\wdm\nf-wdm-iogetiopriorityhint.md">IoGetIoPriorityHint</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_PRIORITY_HINT enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

