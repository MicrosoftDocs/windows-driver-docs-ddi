---
UID: NC:wmilib.WMI_SET_DATABLOCK_CALLBACK
title: WMI_SET_DATABLOCK_CALLBACK
author: windows-driver-content
description: The DpWmiSetDataBlock routine changes all data items in a single instance of a data block. This routine is optional.
old-location: kernel\dpwmisetdatablock.htm
old-project: kernel
ms.assetid: 429c84e4-16da-452a-b26d-a71546299f0b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: DpWmiSetDataBlock, DpWmiSetDataBlock callback function [Kernel-Mode Driver Architecture], WMI_SET_DATABLOCK_CALLBACK, k903_bb4a483a-1ffc-4664-930b-13cc3579086e.xml, kernel.dpwmisetdatablock, wmilib/DpWmiSetDataBlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Desktop
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wmilib.h
api_name:
-	DpWmiSetDataBlock
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# WMI_SET_DATABLOCK_CALLBACK callback


## -description


The <i>DpWmiSetDataBlock</i> routine changes all data items in a single instance of a data block. This routine is optional.


## -parameters




### -param DeviceObject [in]

Pointer to the driver's WDM <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure.


### -param Irp [in]

Pointer to the IRP.


### -param GuidIndex [in]

Specifies the data block by its zero-based index into the list of GUIDs provided by the driver in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a> structure it passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff565834">WmiSystemControl</a>.


### -param InstanceIndex [in]

If the block specified by <i>GuidIndex </i>has multiple instances, <i>InstanceIndex</i> specifies the instance.


### -param BufferSize [in]

Specifies the size in bytes of the buffer at <i>Buffer</i>.


### -param Buffer [in]

Pointer to a buffer that contains new values for the instance.


## -returns



<i>DpWmiSetDataBlock</i> returns STATUS_SUCCESS or an appropriate error status such as the following:

If the driver cannot complete the request immediately, it can return STATUS_PENDING.




## -remarks



WMI calls a driver's <i>DpWmiSetDataBlock</i> routine after the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff565834">WmiSystemControl</a> in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request.

The driver is responsible for validating all input arguments. Specifically, the driver must do the following:

<ul>
<li>
Verify that the <i>GuidIndex</i> value is between zero and GuidCount-1, based on the <b>GuidCount</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a> structure.

</li>
<li>
Verify that the driver has not flagged the specified data block for removal. If the driver recently specified the WMIREG_FLAG_REMOVE_GUID flag in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565811">WMIGUIDREGINFO</a> structure that is contained in a <b>WMILIB_CONTEXT</b> structure, it is possible for a set request to arrive before the removal occurs.

</li>
<li>
Verify that the <i>InstanceIndex</i> value is within the range of instance indexes that are supported by the driver for the data block.

</li>
<li>
Verify that <i>Buffer</i> and <i>BufferSize</i> describe a valid-sized data block, including any padding that exists between data items, and that the contents of the buffer are valid for the data block.

</li>
<li>
Verify that the specified data block is one for which the driver allows caller-initiated modifications. In other words, the driver should not allow modifications to data blocks that you intended to be read-only.

</li>
</ul>
Do not assume the thread context is that of the initiating user-mode application—a higher-level driver might have changed it.

If a driver implements a <i>DpWmiSetDataBlock</i> routine, the driver must place the routine's address in the <b>SetWmiDataBlock</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a> structure that it passes to <a href="https://msdn.microsoft.com/library/windows/hardware/ff565834">WmiSystemControl</a>. If a driver does not implement a <i>DpWmiSetDataBlock</i> routine, it must set <b>SetWmiDataBlock</b> to <b>NULL</b>. In the latter case, WMI returns STATUS_READ_ONLY to the caller.

This routine can be pageable.

For more information about implementing this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540741">Calling WmiSystemControl to Handle WMI IRPs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565834">WmiSystemControl</a>
 

 

