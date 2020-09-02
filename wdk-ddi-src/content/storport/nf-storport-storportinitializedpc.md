---
UID: NF:storport.StorPortInitializeDpc
title: StorPortInitializeDpc function (storport.h)
description: The StorPortInitializeDpc routine initializes a StorPort DPC.
old-location: storage\storportinitializedpc.htm
tech.root: storage
ms.assetid: 0a67304f-c746-46c1-87c4-5d027219e41f
ms.date: 03/29/2018
keywords: ["StorPortInitializeDpc function"]
ms.keywords: StorPortInitializeDpc, StorPortInitializeDpc routine [Storage Devices], storage.storportinitializedpc, storport/StorPortInitializeDpc, storprt_984c8e07-f6c8-452f-a333-dd23a0fdf9f7.xml
req.header: storport.h
req.include-header: Storport.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortInitializeDpc
 - storport/StorPortInitializeDpc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortInitializeDpc
---

# StorPortInitializeDpc function


## -description

The <b>StorPortInitializeDpc</b> routine initializes a StorPort DPC.

## -parameters

### -param DeviceExtension 

[in]
Pointer to the per-adapter device extension.

### -param Dpc 

[out]
Pointer to a buffer where a DPC object of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_dpc">STOR_DPC</a> will be created. The caller must ensure that the size in bytes of this buffer is greater than or equal to <b>sizeof</b>(STOR_DPC).

### -param HwDpcRoutine 

[in]
Pointer to the DPC routine that corresponds to the DPC object pointed to by <i>Dpc</i>. The prototype for this deferred routine is defined in Storport.h as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*PHW_DPC_ROUTINE) 
  IN PSTOR_DPC  Dpc,
  IN PVOID  HwDeviceExtension,
  IN PVOID  SystemArgument1,
  IN PVOID  SystemArgument2
  );</pre>
</td>
</tr>
</table></span></div>

## -remarks

The <b>StorPortInitializeDpc</b> routine must be called during HBA initialization from within the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_passive_initialize_routine">HwStorPassiveInitializeRoutine</a> routine. 

This routine is implemented using inline function definitions, so that miniport drivers that use this routine will not have to link to libraries that are dependent on the version of the operating system. Miniport drivers can use this routine without sacrificing backward compatibility with versions of the operating system that do not support DPCs in storage miniport drivers.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_passive_initialize_routine">HwStorPassiveInitializeRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_dpc">STOR_DPC</a>

