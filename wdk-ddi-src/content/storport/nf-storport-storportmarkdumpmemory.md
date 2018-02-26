---
UID: NF:storport.StorPortMarkDumpMemory
title: StorPortMarkDumpMemory function
author: windows-driver-content
description: A miniport should mark memory used for the dump file or the hibernation file.
old-location: storage\storportmarkdumpmemory.htm
old-project: storage
ms.assetid: DE17FF55-A573-41FE-8979-1DB32AD5B7C0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , D, M, MARK_DUMP_MEMORY_FLAG_PHYSICAL_ADDRESS, P, S, StorPortMarkDumpMemory, StorPortMarkDumpMemory routine [Storage Devices], a, e, k, m, o, p, r, storage.storportmarkdumpmemory, storport/StorPortMarkDumpMemory, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Storport.h
apiname:
-	StorPortMarkDumpMemory
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortMarkDumpMemory function


## -description


A miniport should mark  memory used for the dump file or the hibernation file. Marked memory is retained and remains valid after a resume from hibernation operation. The memory  to mark is specified by an address and range length in a call to <b>StorPortMarkDumpMemory</b>.


## -syntax


````
ULONG StorPortMarkDumpMemory(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Address,
  _In_ PVOID Length,
  _In_ PVOID Flags
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in]

The starting address of the memory range to mark.


### -param Length [in]

The length of the marked memory range.


### -param Flags [in]

Dump memory marking flags. The <i>Flags</i> parameter must be 0 or contain only the following value.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="MARK_DUMP_MEMORY_FLAG_PHYSICAL_ADDRESS"></a><a id="mark_dump_memory_flag_physical_address"></a><dl>
<dt><b>MARK_DUMP_MEMORY_FLAG_PHYSICAL_ADDRESS</b></dt>
</dl>
</td>
<td width="60%">
The address provided in <i>Address</i> is a physical address and not a system virtual address.

</td>
</tr>
</table>
 


## -returns



<b>StorPortMarkDumpMemory</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the routine set the unit attributes successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid flag value was specified in the <i>Flags</i> parameter.

</td>
</tr>
</table>
 




## -remarks



The <b>StorPortMarkDumpMemory</b> routine must only be called by a miniport driver in its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> or <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routines.

If <i>Length</i> = 0, the entire section containing <i>Address</i> is marked.

Miniport drivers should call <b>StorPortMarkDumpMemory</b> to ensure that the memory used by the miniport to generate either the dump file or the hibernation file is identified. At a minimum, miniports should call <b>StorPortMarkDumpMemory</b> when the <b>DumpMode</b> member of <a href="..\storport\ns-storport-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is set to either <b>DUMP_MODE_MARK_MEMORY</b> or <b>DUMP_MODE_HIBER</b>.



