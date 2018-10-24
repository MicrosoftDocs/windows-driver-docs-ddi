---
UID: NS:wudfddi_types._WDFMEMORY_OFFSET
title: "_WDFMEMORY_OFFSET"
author: windows-driver-content
description: The WDFMEMORY_OFFSET structure describes the location and size of information that is accessed within a memory block.
old-location: wdf\wdfmemory_offset_umdf.htm
tech.root: wdf
ms.assetid: 960710f7-15b1-4815-a33a-0e903d0a4193
ms.date: 02/26/2018
ms.keywords: "*PWDFMEMORY_OFFSET, PWDFMEMORY_OFFSET, PWDFMEMORY_OFFSET structure pointer, WDFMEMORY_OFFSET, WDFMEMORY_OFFSET structure, _WDFMEMORY_OFFSET, umdf.wdfmemory_offset, umdfstructs_919b5e02-39d3-4f06-867d-43133c008e85.xml, wdf.wdfmemory_offset_umdf, wudfddi_types/PWDFMEMORY_OFFSET, wudfddi_types/WDFMEMORY_OFFSET"
ms.topic: struct
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_types.h
api_name:
-	WDFMEMORY_OFFSET
product:
- Windows
targetos: Windows
req.typenames: WDFMEMORY_OFFSET, *PWDFMEMORY_OFFSET
---

# _WDFMEMORY_OFFSET structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure describes the location and size of information that is accessed within a memory block.


## -struct-fields




### -field BufferOffset

The offset, in bytes, into the memory block where information is first accessed. 


### -field BufferLength

The size, in bytes, of the information that is accessed in the memory block. 


## -remarks



A UMDF driver supplies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560145">IWDFMemory::CopyFromMemory</a> method to describe information to copy from a memory block.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560145">IWDFMemory::CopyFromMemory</a>
 

 

