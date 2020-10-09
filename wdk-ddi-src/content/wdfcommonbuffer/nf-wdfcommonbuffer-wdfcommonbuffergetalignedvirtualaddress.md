---
UID: NF:wdfcommonbuffer.WdfCommonBufferGetAlignedVirtualAddress
title: WdfCommonBufferGetAlignedVirtualAddress function (wdfcommonbuffer.h)
description: The WdfCommonBufferGetAlignedVirtualAddress method returns the virtual address that is associated with a specified common buffer.
old-location: wdf\wdfcommonbuffergetalignedvirtualaddress.htm
tech.root: wdf
ms.assetid: 6874a1bc-e16e-4052-85a4-dba617a69ccd
ms.date: 02/26/2018
keywords: ["WdfCommonBufferGetAlignedVirtualAddress function"]
ms.keywords: DFCommonBufferObjectRef_469df6c0-51ef-480a-93fe-dee452eaf216.xml, WdfCommonBufferGetAlignedVirtualAddress, WdfCommonBufferGetAlignedVirtualAddress method, kmdf.wdfcommonbuffergetalignedvirtualaddress, wdf.wdfcommonbuffergetalignedvirtualaddress, wdfcommonbuffer/WdfCommonBufferGetAlignedVirtualAddress
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfCommonBufferGetAlignedVirtualAddress
 - wdfcommonbuffer/WdfCommonBufferGetAlignedVirtualAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfCommonBufferGetAlignedVirtualAddress
---

# WdfCommonBufferGetAlignedVirtualAddress function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCommonBufferGetAlignedVirtualAddress</b> method returns the virtual address that is associated with a specified common buffer.

## -parameters

### -param CommonBuffer 

[in]
A handle to a common buffer object that the driver obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffercreate">WdfCommonBufferCreate</a>.

## -returns

<b>WdfCommonBufferGetAlignedVirtualAddress</b> returns the virtual address of the buffer that is associated with the common buffer that the <i>CommonBuffer</i> parameter specifies.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If the driver called <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetalignmentrequirement">WdfDeviceSetAlignmentRequirement</a> to set a buffer alignment requirement, the framework aligns the common buffer according to that alignment requirement.

For more information about common buffers, see <a href="/windows-hardware/drivers/wdf/using-common-buffers">Using Common Buffers</a>



#### Examples

For a code example that uses <b>WdfCommonBufferGetAlignedVirtualAddress</b>, see <a href="/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffercreate">WdfCommonBufferCreate</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffercreate">WdfCommonBufferCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress">WdfCommonBufferGetAlignedLogicalAddress</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetalignmentrequirement">WdfDeviceSetAlignmentRequirement</a>