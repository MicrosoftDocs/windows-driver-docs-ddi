---
UID: NE:wdm._IO_PRIORITY_HINT
title: _IO_PRIORITY_HINT (wdm.h)
description: The IO_PRIORITY_HINT enumeration type specifies the priority hint for an IRP.
old-location: kernel\io_priority_hint.htm
tech.root: kernel
ms.assetid: 38d19398-b34f-4934-b643-df119ebd9711
ms.date: 04/30/2018
ms.keywords: IO_PRIORITY_HINT, IO_PRIORITY_HINT enumeration [Kernel-Mode Driver Architecture], IoPriorityCritical, IoPriorityHigh, IoPriorityLow, IoPriorityNormal, IoPriorityVeryLow, MaxIoPriorityTypes, _IO_PRIORITY_HINT, kernel.io_priority_hint, sysenum_0b8187d9-c762-45d2-a310-294c3c696608.xml, wdm/IO_PRIORITY_HINT, wdm/IoPriorityCritical, wdm/IoPriorityHigh, wdm/IoPriorityLow, wdm/IoPriorityNormal, wdm/IoPriorityVeryLow, wdm/MaxIoPriorityTypes
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IO_PRIORITY_HINT
product:
- Windows
targetos: Windows
req.typenames: IO_PRIORITY_HINT
---

# _IO_PRIORITY_HINT enumeration


## -description


The <b>IO_PRIORITY_HINT</b> enumeration type specifies the <a href="https://msdn.microsoft.com/c34afff2-32f2-451b-ab16-ff048d5c3204">priority hint</a> for an IRP.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549265">IoGetIoPriorityHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549710">IoSetIoPriorityHint</a>
 

 

