---
UID: NS:ndkpi._NDK_OBJECT_HEADER
title: "_NDK_OBJECT_HEADER"
author: windows-driver-content
description: The NDK_OBJECT_HEADER structure specifies the object version, type, and other information. It is used in the Header member of every NDK object.
old-location: netvista\ndk_object_header.htm
tech.root: netvista
ms.assetid: 12E3ED4A-F078-4489-BC84-69EE735CAEF8
ms.date: 05/02/2018
ms.keywords: NDK_OBJECT_HEADER, NDK_OBJECT_HEADER structure [Network Drivers Starting with Windows Vista], PNDK_OBJECT_HEADER, PNDK_OBJECT_HEADER structure pointer [Network Drivers Starting with Windows Vista], _NDK_OBJECT_HEADER, ndkpi/NDK_OBJECT_HEADER, ndkpi/PNDK_OBJECT_HEADER, netvista.ndk_object_header
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
-	ndkpi.h
api_name:
-	NDK_OBJECT_HEADER
product:
- Windows
targetos: Windows
req.typenames: NDK_OBJECT_HEADER
---

# _NDK_OBJECT_HEADER structure


## -description


The <b>NDK_OBJECT_HEADER</b> structure specifies the object version, type, and other  information.

It is used in the <b>Header</b> member of every NDK object.


## -struct-fields




### -field Version

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a> structure that contains the revision number of the NDK object.


### -field ObjectType

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh439930">NDK_OBJECT_TYPE</a> enumeration value that specifies the NDK object type. You can use this member to identify an NDK object's type in a memory dump.

This member is required and cannot be zero.


### -field NdkReserved

A reserved block in an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439929">NDK_OBJECT_HEADER_RESERVED_BLOCK</a> structure.


## -remarks



When an NDK provider creates an NDK object instance, the <b>Header</b> member must be initialized as follows:

<ul>
<li>
For Windows Server 2012, set the <b>Version</b> member to 1.1. To do this, set both the <b>Major</b> and <b>Minor</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a> structure to 1.

</li>
<li>
For Windows Server 2012 R2, set the <b>Version</b> member to 1.2. To do this, set the <b>Major</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a> structure to 1 and the <b>Minor</b> member to 2.

</li>
<li>
Set the <b>ObjectType</b>  member to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439930">NDK_OBJECT_TYPE</a> value.

</li>
<li>
Set the  <b>NdkReserved</b> member to zero. The NDK provider must not modify this member until the object is closed.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439852">NDK_CONNECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439871">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439901">NDK_FN_INVALIDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439918">NDK_LISTENER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439926">NDK_MW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439929">NDK_OBJECT_HEADER_RESERVED_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439930">NDK_OBJECT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439931">NDK_PD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439937">NDK_SHARED_ENDPOINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a>
 

 

