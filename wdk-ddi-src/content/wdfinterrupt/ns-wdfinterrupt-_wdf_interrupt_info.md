---
UID: NS:wdfinterrupt._WDF_INTERRUPT_INFO
title: _WDF_INTERRUPT_INFO (wdfinterrupt.h)
description: The WDF_INTERRUPT_INFO structure contains information about a device's interrupt resource.
old-location: wdf\wdf_interrupt_info.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_INTERRUPT_INFO structure"]
ms.keywords: "*PWDF_INTERRUPT_INFO, DFInterruptObjectRef_3f4ade63-40f9-4d5a-96a0-e4f7013171d5.xml, PWDF_INTERRUPT_INFO, PWDF_INTERRUPT_INFO structure pointer, WDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO structure, _WDF_INTERRUPT_INFO, kmdf.wdf_interrupt_info, wdf.wdf_interrupt_info, wdfinterrupt/PWDF_INTERRUPT_INFO, wdfinterrupt/WDF_INTERRUPT_INFO"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
req.typenames: WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
f1_keywords:
 - _WDF_INTERRUPT_INFO
 - wdfinterrupt/_WDF_INTERRUPT_INFO
 - PWDF_INTERRUPT_INFO
 - wdfinterrupt/PWDF_INTERRUPT_INFO
 - WDF_INTERRUPT_INFO
 - wdfinterrupt/WDF_INTERRUPT_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfinterrupt.h
api_name:
 - _WDF_INTERRUPT_INFO
 - PWDF_INTERRUPT_INFO
 - WDF_INTERRUPT_INFO
---

# _WDF_INTERRUPT_INFO structure (wdfinterrupt.h)


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_INFO</b> structure contains information about a device's interrupt resource.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Reserved1

This member is reserved for future use.

### -field TargetProcessorSet

A [**KAFFINITY**](/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)-typed value that specifies the interrupt's processor affinity.

### -field Reserved2

This member is reserved for future use.

### -field MessageNumber

If the <b>MessageSignaled</b> member is <b>TRUE</b>, this is the interrupt's message number.

### -field Vector

The interrupt vector.

### -field Irql

The IRQL at which the device interrupts.

### -field Mode

A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a>-typed enumerator that indicates whether the interrupt is level-triggered or edge-triggered.

### -field Polarity

A <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_polarity">WDF_INTERRUPT_POLARITY</a>-typed enumerator that identifies the interrupt signal's polarity.

### -field MessageSignaled

A Boolean value that, if <b>TRUE</b>, indicates that the interrupt is message-signaled. If <b>FALSE</b>, the interrupt is not message-signaled.

### -field ShareDisposition

A CM_SHARE_DISPOSITION-typed enumerator that indicates whether the interrupt is being shared. The value is <b>CmResourceShareShared</b> if the interrupt is being shared or <b>CmResourceShareDeviceExclusive</b> if the interrupt is not being shared. The CM_SHARE_DISPOSITION enumeration type is defined in <i>Wdm.h</i>.

### -field Group

A value that identifies the processor group that the <b>TargetProcessorSet</b> member applies to. This value is zero if the computer has only one processor group or if the operating system does not support processor groups. The <b>Group</b> member is available in version 1.9 and later versions of KMDF.

## -remarks

The <b>WDF_INTERRUPT_INFO</b> structure is used as input to the <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptgetinfo">WdfInterruptGetInfo</a> method. To initialize a <b>WDF_INTERRUPT_INFO</b> structure, your driver should call <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_info_init">WDF_INTERRUPT_INFO_INIT</a> before calling <b>WdfInterruptGetInfo</b>.

## -see-also

[**KAFFINITY**](/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_info_init">WDF_INTERRUPT_INFO_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_polarity">WDF_INTERRUPT_POLARITY</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptgetinfo">WdfInterruptGetInfo</a>

