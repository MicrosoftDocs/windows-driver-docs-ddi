---
UID: NF:wdfcommonbuffer.WdfCommonBufferGetAlignedLogicalAddress
title: WdfCommonBufferGetAlignedLogicalAddress function
author: windows-driver-content
description: The WdfCommonBufferGetAlignedLogicalAddress method returns the logical address that is associated with a specified common buffer.
old-location: wdf\wdfcommonbuffergetalignedlogicaladdress.htm
tech.root: wdf
ms.assetid: 6222db07-5aba-467c-94a5-18493dfb1524
ms.date: 02/26/2018
ms.keywords: DFCommonBufferObjectRef_8381c500-1cd1-4271-9679-33a213a2307f.xml, WdfCommonBufferGetAlignedLogicalAddress, WdfCommonBufferGetAlignedLogicalAddress method, kmdf.wdfcommonbuffergetalignedlogicaladdress, wdf.wdfcommonbuffergetalignedlogicaladdress, wdfcommonbuffer/WdfCommonBufferGetAlignedLogicalAddress
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
-	WdfCommonBufferGetAlignedLogicalAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCommonBufferGetAlignedLogicalAddress function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCommonBufferGetAlignedLogicalAddress</b> method returns the logical address that is associated with a specified common buffer. 


## -parameters




### -param CommonBuffer [in]

A handle to a common buffer object that the driver obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>.  


## -returns



<b>WdfCommonBufferGetAlignedLogicalAddress</b> returns the logical address of the buffer that is associated with the common buffer that the <i>CommonBuffer</i> parameter specifies.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Logical addresses are mapped addresses that devices use to access physical memory.

If the driver called <a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a> to set a buffer alignment requirement, the framework aligns the common buffer according to that alignment requirement.

For more information about common buffers, see <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>



#### Examples

For a code example that uses <b>WdfCommonBufferGetAlignedLogicalAddress</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545820">WdfCommonBufferGetAlignedVirtualAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a>
 

 

