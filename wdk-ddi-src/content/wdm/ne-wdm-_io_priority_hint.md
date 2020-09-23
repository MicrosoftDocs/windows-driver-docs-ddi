---
UID: NE:wdm._IO_PRIORITY_HINT
title: _IO_PRIORITY_HINT (wdm.h)
description: The IO_PRIORITY_HINT enumeration type specifies the priority hint for an IRP.
old-location: kernel\io_priority_hint.htm
tech.root: kernel
ms.assetid: 38d19398-b34f-4934-b643-df119ebd9711
ms.date: 04/30/2018
keywords: ["IO_PRIORITY_HINT enumeration"]
ms.keywords: IO_PRIORITY_HINT, IO_PRIORITY_HINT enumeration [Kernel-Mode Driver Architecture], IoPriorityCritical, IoPriorityHigh, IoPriorityLow, IoPriorityNormal, IoPriorityVeryLow, MaxIoPriorityTypes, _IO_PRIORITY_HINT, kernel.io_priority_hint, sysenum_0b8187d9-c762-45d2-a310-294c3c696608.xml, wdm/IO_PRIORITY_HINT, wdm/IoPriorityCritical, wdm/IoPriorityHigh, wdm/IoPriorityLow, wdm/IoPriorityNormal, wdm/IoPriorityVeryLow, wdm/MaxIoPriorityTypes
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
targetos: Windows
req.typenames: IO_PRIORITY_HINT
f1_keywords:
 - _IO_PRIORITY_HINT
 - wdm/_IO_PRIORITY_HINT
 - IO_PRIORITY_HINT
 - wdm/IO_PRIORITY_HINT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - IO_PRIORITY_HINT
---

# _IO_PRIORITY_HINT enumeration


## -description

The <b>IO_PRIORITY_HINT</b> enumeration type specifies the <a href="/windows-hardware/drivers/kernel/using-irp-priority-hints">priority hint</a> for an IRP.

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

For more information about priority hints, see <a href="/windows-hardware/drivers/kernel/using-irp-priority-hints">Using IRP Priority Hints</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetiopriorityhint">IoGetIoPriorityHint</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetiopriorityhint">IoSetIoPriorityHint</a>