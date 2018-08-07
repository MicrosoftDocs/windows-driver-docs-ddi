---
UID: NF:wdfcommonbuffer.WdfCommonBufferGetAlignedVirtualAddress
title: WdfCommonBufferGetAlignedVirtualAddress function
author: windows-driver-content
description: The WdfCommonBufferGetAlignedVirtualAddress method returns the virtual address that is associated with a specified common buffer.
old-location: wdf\wdfcommonbuffergetalignedvirtualaddress.htm
tech.root: wdf
ms.assetid: 6874a1bc-e16e-4052-85a4-dba617a69ccd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFCommonBufferObjectRef_469df6c0-51ef-480a-93fe-dee452eaf216.xml, WdfCommonBufferGetAlignedVirtualAddress, WdfCommonBufferGetAlignedVirtualAddress method, kmdf.wdfcommonbuffergetalignedvirtualaddress, wdf.wdfcommonbuffergetalignedvirtualaddress, wdfcommonbuffer/WdfCommonBufferGetAlignedVirtualAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfCommonBufferGetAlignedVirtualAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCommonBufferGetAlignedVirtualAddress function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCommonBufferGetAlignedVirtualAddress</b> method returns the virtual address that is associated with a specified common buffer. 


## -parameters




### -param CommonBuffer [in]

A handle to a common buffer object that the driver obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>.  


## -returns



<b>WdfCommonBufferGetAlignedVirtualAddress</b> returns the virtual address of the buffer that is associated with the common buffer that the <i>CommonBuffer</i> parameter specifies.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the driver called <a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a> to set a buffer alignment requirement, the framework aligns the common buffer according to that alignment requirement.

For more information about common buffers, see <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>



#### Examples

For a code example that uses <b>WdfCommonBufferGetAlignedVirtualAddress</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545814">WdfCommonBufferGetAlignedLogicalAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a>
 

 

