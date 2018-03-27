---
UID: NS:ntifs._NETWORK_OPEN_ECP_CONTEXT_V0
title: "_NETWORK_OPEN_ECP_CONTEXT_V0"
author: windows-driver-content
description: The NETWORK_OPEN_ECP_CONTEXT_V0 structure is used to interpret network ECP contexts on files.
old-location: ifsk\network_open_ecp_context_v0.htm
old-project: ifsk
ms.assetid: 447d623a-88cb-4d3d-8b05-4f5624c707ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNETWORK_OPEN_ECP_CONTEXT_V0, ECP_Structures_8bd64f25-774a-4f87-a903-07ce0a3c0989.xml, NETWORK_OPEN_ECP_CONTEXT_V0, NETWORK_OPEN_ECP_CONTEXT_V0 structure [Installable File System Drivers], PNETWORK_OPEN_ECP_CONTEXT_V0, PNETWORK_OPEN_ECP_CONTEXT_V0 structure pointer [Installable File System Drivers], _NETWORK_OPEN_ECP_CONTEXT_V0, ifsk.network_open_ecp_context_v0, ntifs/NETWORK_OPEN_ECP_CONTEXT_V0, ntifs/PNETWORK_OPEN_ECP_CONTEXT_V0"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 7.
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
-	ntifs.h
api_name:
-	NETWORK_OPEN_ECP_CONTEXT_V0
product: Windows
targetos: Windows
req.typenames: NETWORK_OPEN_ECP_CONTEXT_V0, *PNETWORK_OPEN_ECP_CONTEXT_V0
---

# _NETWORK_OPEN_ECP_CONTEXT_V0 structure


## -description


The NETWORK_OPEN_ECP_CONTEXT_V0 structure is used to interpret network ECP contexts on files. 


## -struct-fields




### -field Size

The size, in bytes, of this structure. 


### -field Reserved

Reserved. Must be set to zero. 


### -field DUMMYSTRUCTNAME

A structure that contains restrictions to apply for opening the file and to apply to the file after it is opened.  


### -field DUMMYSTRUCTNAME.in

A structure in the DUMMYSTRUCTNAME structure that contains restrictions for opening a file.




### -field DUMMYSTRUCTNAME.in.Location

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550908">NETWORK_OPEN_LOCATION_QUALIFIER</a>-typed value that specifies the location restriction to attach to the file. 


### -field DUMMYSTRUCTNAME.in.Integrity

This member is currently not implemented and should be ignored. 

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550902">NETWORK_OPEN_INTEGRITY_QUALIFIER</a>-typed value that specifies the integrity restriction to attach to the file. 


### -field DUMMYSTRUCTNAME.out

A structure in the DUMMYSTRUCTNAME structure that contains information that a file provides after it is opened.




### -field DUMMYSTRUCTNAME.out.Location

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550908">NETWORK_OPEN_LOCATION_QUALIFIER</a>-typed value that specifies the location restriction to attach to the file. 


### -field DUMMYSTRUCTNAME.out.Integrity

This member is currently not implemented and should be ignored. 

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550902">NETWORK_OPEN_INTEGRITY_QUALIFIER</a>-typed value that specifies the integrity restriction to attach to the file. 


## -remarks



For information about how to use ECPs to associate extra information with a file when the file is created, see <a href="https://msdn.microsoft.com/e32aeec6-1a0a-4d21-8358-89d9fc0a15eb">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>. 

The NETWORK_OPEN_ECP_CONTEXT_V0 structure is read-only. You should use it to retrieve information about the network ECP context on a file only. For more information about this issue, see <a href="https://msdn.microsoft.com/6acb4be4-a7aa-431d-b2d8-3ef6d41cb4ef">System-Defined ECPs</a>.

If a caller must verify that the file system acknowledged the NETWORK_OPEN_ECP_CONTEXT_V0 context structure, the caller should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546808">FsRtlIsEcpAcknowledged</a> routine on the ECP after the operation is complete.

In most cases, drivers that run on Windows Vista and later versions of Windows use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550896">NETWORK_OPEN_ECP_CONTEXT</a> structure to interpret network ECP contexts on files. However, drivers that run on Windows 7 and later versions of Windows and that must interpret network ECP contexts on files that reside on Windows Vista must use the NETWORK_OPEN_ECP_CONTEXT_V0 structure instead. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550896">NETWORK_OPEN_ECP_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550902">NETWORK_OPEN_INTEGRITY_QUALIFIER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550908">NETWORK_OPEN_LOCATION_QUALIFIER</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20NETWORK_OPEN_ECP_CONTEXT_V0 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

