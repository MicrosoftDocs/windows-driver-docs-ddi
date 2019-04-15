---
UID: NF:ndis.NdisUnmapFile
title: NdisUnmapFile function (ndis.h)
description: The NdisUnmapFile function releases a virtual address mapping of a file previously set up with the NdisMapFile function.
old-location: netvista\ndisunmapfile.htm
tech.root: netvista
ms.assetid: 20ba1eef-2377-4e17-a2ff-002f1bbe15f0
ms.date: 05/02/2018
ms.keywords: NdisUnmapFile, NdisUnmapFile function [Network Drivers Starting with Windows Vista], ndis/NdisUnmapFile, ndis_file_ref_5be88800-5866-4969-8534-2d76953bf4de.xml, netvista.ndisunmapfile
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisUnmapFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisUnmapFile function


## -description


The
  <b>NdisUnmapFile</b> function releases a virtual address mapping of a file previously set up with the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff562785">NdisMapFile</a> function.


## -parameters




### -param FileHandle [in]

The handle that was returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563728">NdisOpenFile</a> function.


## -returns



None




## -remarks



To reduce resource usage, a miniport driver should always call 
    <b>NdisUnmapFile</b> when it no longer needs exclusive access to the contents of a file that it opened.
    Such a driver can map and unmap the file as necessary, using alternating calls to 
    <b>NdisMapFile</b> and 
    <b>NdisUnmapFile</b> until it releases the file handle with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561645">NdisCloseFile</a> function.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561645">NdisCloseFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562785">NdisMapFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563728">NdisOpenFile</a>
 

 

