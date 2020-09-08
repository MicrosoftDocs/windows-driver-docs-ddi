---
UID: NF:iointex.WdmlibIoGetAffinityInterrupt
title: WdmlibIoGetAffinityInterrupt function (iointex.h)
description: The WdmlibIoGetAffinityInterrupt function gets the group affinity of an interrupt object.
old-location: kernel\wdmlibiogetaffinityinterrupt.htm
tech.root: kernel
ms.assetid: E9E80EB4-C20B-4025-957B-32DC6FAE7F38
ms.date: 04/30/2018
keywords: ["WdmlibIoGetAffinityInterrupt function"]
ms.keywords: IoGetAffinityInterrupt, WdmlibIoGetAffinityInterrupt, WdmlibIoGetAffinityInterrupt function [Kernel-Mode Driver Architecture], iointex/IoGetAffinityInterrupt, iointex/WdmlibIoGetAffinityInterrupt, kernel.wdmlibiogetaffinityinterrupt
req.header: iointex.h
req.include-header: Iointex.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdmlibIoGetAffinityInterrupt
 - iointex/WdmlibIoGetAffinityInterrupt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WdmlibIoGetAffinityInterrupt
 - IoGetAffinityInterrupt
---

# WdmlibIoGetAffinityInterrupt function


## -description

The <b>WdmlibIoGetAffinityInterrupt</b> function gets the group affinity of an interrupt object.

## -parameters

### -param InterruptObject 

[in]
A pointer to an interrupt object. This parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KINTERRUPT</a> structure that represents a registration by a driver to receive device interrupts. The structure is opaque. The caller obtained this pointer value in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iointex/nf-iointex-wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a> routine.

### -param GroupAffinity 

[out]
A pointer to a caller-allocated buffer into which the routine writes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a> structure that specifies the group affinity of the interrupt object that <i>InterruptObject</i> points to. This buffer must be large enough to contain the structure.

## -returns

<b>WdmlibIoGetAffinityInterrupt</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>InterruptObject</i> parameter does not point to a valid interrupt object. 

</td>
</tr>
</table>

## -remarks

A kernel-mode driver calls this routine to get the set of logical processors on which the driver's registered interrupt service routine (ISR) can receive device interrupts. This set of processors is described by a <b>GROUP_AFFINITY</b> structure, which specifies a group number and an affinity mask. All the processors that are assigned to a particular ISR registration must belong to the same group.

The driver registered the ISR in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iointex/nf-iointex-wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a> or <b>IoConnectInterrupt</b> routine.

In Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iointex/nf-iointex-wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a> and <b>IoConnectInterrupt</b> assign device interrupts only to logical processors in group 0. This is by default. A driver can specify a different interrupt affinity for its device in an INF file or in its response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> request. For more information about how to change the interrupt affinity, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=147914">Supporting Systems That Have More Than 64 Processors</a> white paper on the  WHDC website.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KINTERRUPT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iointex/nf-iointex-wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a>

