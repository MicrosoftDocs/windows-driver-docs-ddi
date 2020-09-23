---
UID: NE:wudfinterrupt._WDF_INTERRUPT_PRIORITY
title: _WDF_INTERRUPT_PRIORITY (wudfinterrupt.h)
description: The WDF_INTERRUPT_PRIORITY enumeration type identifies relative priorities for device interrupts.
old-location: wdf\wdf_interrupt_priority_umdf.htm
tech.root: wdf
ms.assetid: ECAB84B8-1C39-473C-A6AE-41D1EBDB1FF4
ms.date: 02/26/2018
keywords: ["WDF_INTERRUPT_PRIORITY enumeration"]
ms.keywords: "*PWDF_INTERRUPT_PRIORITY, PWDF_INTERRUPT_PRIORITY, PWDF_INTERRUPT_PRIORITY enumeration pointer, WDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY enumeration, WdfIrqPriorityHigh, WdfIrqPriorityLow, WdfIrqPriorityNormal, WdfIrqPriorityUndefined, _WDF_INTERRUPT_PRIORITY, umdf.wdf_interrupt_priority, wdf.wdf_interrupt_priority_umdf, wudfinterrupt/PWDF_INTERRUPT_PRIORITY, wudfinterrupt/WDF_INTERRUPT_PRIORITY, wudfinterrupt/WdfIrqPriorityHigh, wudfinterrupt/WdfIrqPriorityLow, wudfinterrupt/WdfIrqPriorityNormal, wudfinterrupt/WdfIrqPriorityUndefined"
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
f1_keywords:
 - _WDF_INTERRUPT_PRIORITY
 - wudfinterrupt/_WDF_INTERRUPT_PRIORITY
 - PWDF_INTERRUPT_PRIORITY
 - wudfinterrupt/PWDF_INTERRUPT_PRIORITY
 - WDF_INTERRUPT_PRIORITY
 - wudfinterrupt/WDF_INTERRUPT_PRIORITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfinterrupt.h
api_name:
 - WDF_INTERRUPT_PRIORITY
---

# _WDF_INTERRUPT_PRIORITY enumeration (wudfinterrupt.h)


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_priority">WDF_INTERRUPT_PRIORITY</a> enumeration type identifies relative priorities for device interrupts.

## -enum-fields

### -field WdfIrqPriorityUndefined

The relative priority of a device's interrupt is undefined.

### -field WdfIrqPriorityLow

The device's interrupt has a relatively low priority, typically because the interrupt does not have to be serviced immediately.

### -field WdfIrqPriorityNormal

The device's interrupt priority is neither relatively low nor relatively high.

### -field WdfIrqPriorityHigh

The device's interrupt has a relatively high priority, typically because the interrupt must be serviced immediately.

## -remarks

The <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_priority">WDF_INTERRUPT_PRIORITY</a> enumeration type is used as input to the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-setpolicy">IWDFInterrupt::SetPolicy</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-setpolicy">IWDFInterrupt::SetPolicy</a>