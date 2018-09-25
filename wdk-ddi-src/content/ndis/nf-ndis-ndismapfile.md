---
UID: NF:ndis.NdisMapFile
title: NdisMapFile function
author: windows-driver-content
description: The NdisMapFile function maps an already open file into a caller-accessible buffer if the file is currently unmapped.
old-location: netvista\ndismapfile.htm
tech.root: netvista
ms.assetid: 965bb4c7-826d-425b-b10d-2d5a29ca0f91
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisMapFile, NdisMapFile function [Network Drivers Starting with Windows Vista], VOID, ndis/NdisMapFile, ndis_file_ref_5bc73f64-8379-45bb-a37b-fe9a946af119.xml, netvista.ndismapfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Video.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMapFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMapFile (NDIS 5.1)) in Windows   XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMapFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMapFile function


## -description


The 
  <b>NdisMapFile</b> function maps an already open file into a caller-accessible buffer if the file is
  currently unmapped.


## -parameters




### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of the mapping
     operation, which can be one of the following:
     





#### NDIS_STATUS_SUCCESS

The caller has exclusive access to the file contents until the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff564641">NdisUnmapFile</a> function is called.



#### NDIS_STATUS_ALREADY_MAPPED

The caller cannot access the file contents at this time.


### -param MappedBuffer [out]

A pointer to a caller-supplied variable in which this function returns the base virtual address of
     the mapped file contents or <b>NULL</b>.


### -param FileHandle [in]

The handle that was returned by a preceding call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563728">NdisOpenFile</a> function.


## -returns



None




## -remarks



<b>NdisMapFile</b> associates (maps) a virtual address range with an opened file so the driver can access
    the file contents. 
    <b>NdisMapFile</b> allows only one mapping of a particular file to be outstanding at any time.
    Consequently, a successful caller is given exclusive access to the file data until 
    <b>NdisUnmapFile</b> or the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561645">NdisCloseFile</a> function is called.

A miniport driver can map and unmap such an open file as necessary, using alternating calls to 
    <b>NdisMapFile</b> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564641">NdisUnmapFile</a>. A call to 
    <b>NdisCloseFile</b> releases the 
    <i>FileHandle</i> and deallocates the buffer containing the file contents.

A miniport driver can call 
    <b>NdisMapFile</b> only during initialization.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561645">NdisCloseFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563728">NdisOpenFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564641">NdisUnmapFile</a>
 

 

