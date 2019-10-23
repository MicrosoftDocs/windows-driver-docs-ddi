---
UID: NF:ndis.NdisCloseFile
title: NdisCloseFile function (ndis.h)
description: The NdisCloseFile function releases a handle returned by the NdisOpenFile function and frees the memory allocated to hold the file contents when it was opened.
old-location: netvista\ndisclosefile.htm
tech.root: netvista
ms.assetid: a12f7597-cfe7-466f-a5b5-aafd885d5adf
ms.date: 05/02/2018
ms.keywords: NdisCloseFile, NdisCloseFile function [Network Drivers Starting with Windows Vista], ndis/NdisCloseFile, ndis_file_ref_17933dee-e6d5-4b5d-a078-84617c38c46c.xml, netvista.ndisclosefile
ms.topic: function
f1_keywords:
 - "ndis/NdisCloseFile"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCloseFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisCloseFile (NDIS 5.1)) in Windows   XP.
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
- NdisCloseFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCloseFile function


## -description


The 
  <b>NdisCloseFile</b> function releases a handle returned by the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenfile">NdisOpenFile</a> function and frees the memory
  allocated to hold the file contents when it was opened.


## -parameters




### -param FileHandle [in]

The handle that was returned in a preceding call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenfile">NdisOpenFile</a> function.


## -returns



None




## -remarks



For miniport drivers, calls to this function are valid only during initialization. If the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
    calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenfile">NdisOpenFile</a> function, it must call 
    <b>NdisCloseFile</b> before it returns control.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismapfile">NdisMapFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenfile">NdisOpenFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisunmapfile">NdisUnmapFile</a>
 

 

