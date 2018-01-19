---
UID: NF:iointex.WdmlibIoGetAffinityInterrupt
title: WdmlibIoGetAffinityInterrupt function
author: windows-driver-content
description: The WdmlibIoGetAffinityInterrupt function gets the group affinity of an interrupt object.
old-location: kernel\wdmlibiogetaffinityinterrupt.htm
old-project: kernel
ms.assetid: E9E80EB4-C20B-4025-957B-32DC6FAE7F38
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: WdmlibIoGetAffinityInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iointex.h
req.include-header: Iointex.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WdmlibIoGetAffinityInterrupt,IoGetAffinityInterrupt
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
req.typenames: LUID
---

# WdmlibIoGetAffinityInterrupt function



## -description
The <b>WdmlibIoGetAffinityInterrupt</b> function gets the group affinity of an interrupt object. 



## -syntax

````
NTSTATUS WdmlibIoGetAffinityInterrupt(
  _In_  PKINTERRUPT     InterruptObject,
  _Out_ PGROUP_AFFINITY GroupAffinity
);
````


## -parameters

### -param InterruptObject [in]

A pointer to an interrupt object. This parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure that represents a registration by a driver to receive device interrupts. The structure is opaque. The caller obtained this pointer value in a previous call to the <a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a> or <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a> routine.


### -param GroupAffinity [out]

A pointer to a caller-allocated buffer into which the routine writes a <a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a> structure that specifies the group affinity of the interrupt object that <i>InterruptObject</i> points to. This buffer must be large enough to contain the structure.


## -returns
<b>WdmlibIoGetAffinityInterrupt</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>InterruptObject</i> parameter does not point to a valid interrupt object. 

 


## -remarks
A kernel-mode driver calls this routine to get the set of logical processors on which the driver's registered interrupt service routine (ISR) can receive device interrupts. This set of processors is described by a <b>GROUP_AFFINITY</b> structure, which specifies a group number and an affinity mask. All the processors that are assigned to a particular ISR registration must belong to the same group.

The driver registered the ISR in a previous call to the <a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a> or <b>IoConnectInterrupt</b> routine.

In Windows 7, <a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a> and <b>IoConnectInterrupt</b> assign device interrupts only to logical processors in group 0. This is by default. A driver can specify a different interrupt affinity for its device in an INF file or in its response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550874">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> request. For more information about how to change the interrupt affinity, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=147914">Supporting Systems That Have More Than 64 Processors</a> white paper on the  WHDC website.


## -see-also
<dl>
<dt>
<a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>
</dt>
<dt>
<a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550874">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WdmlibIoGetAffinityInterrupt function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

