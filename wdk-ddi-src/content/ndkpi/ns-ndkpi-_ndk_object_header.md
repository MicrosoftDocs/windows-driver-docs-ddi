---
UID: NS:ndkpi._NDK_OBJECT_HEADER
title: "_NDK_OBJECT_HEADER"
author: windows-driver-content
description: The NDK_OBJECT_HEADER structure specifies the object version, type, and other information. It is used in the Header member of every NDK object.
old-location: netvista\ndk_object_header.htm
old-project: netvista
ms.assetid: 12E3ED4A-F078-4489-BC84-69EE735CAEF8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDK_OBJECT_HEADER, NDK_OBJECT_HEADER structure [Network Drivers Starting with Windows Vista], PNDK_OBJECT_HEADER, PNDK_OBJECT_HEADER structure pointer [Network Drivers Starting with Windows Vista], _NDK_OBJECT_HEADER, ndkpi/NDK_OBJECT_HEADER, ndkpi/PNDK_OBJECT_HEADER, netvista.ndk_object_header
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_OBJECT_HEADER
product: Windows
targetos: Windows
req.typenames: NDK_OBJECT_HEADER
---

# _NDK_OBJECT_HEADER structure


## -description


The <b>NDK_OBJECT_HEADER</b> structure specifies the object version, type, and other  information.

It is used in the <b>Header</b> member of every NDK object.


## -syntax


````
typedef struct _NDK_OBJECT_HEADER {
  NDK_VERSION                      Version;
  NDK_OBJECT_TYPE                  ObjectType;
  NDK_OBJECT_HEADER_RESERVED_BLOCK NdkReserved;
} NDK_OBJECT_HEADER, *PNDK_OBJECT_HEADER;
````


## -struct-fields




### -field Version

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a> structure that contains the revision number of the NDK object.


### -field ObjectType

An <a href="..\ndkpi\ne-ndkpi-_ndk_object_type.md">NDK_OBJECT_TYPE</a> enumeration value that specifies the NDK object type. You can use this member to identify an NDK object's type in a memory dump.

This member is required and cannot be zero.


### -field NdkReserved

A reserved block in an <a href="..\ndkpi\ns-ndkpi-_ndk_object_header_reserved_block.md">NDK_OBJECT_HEADER_RESERVED_BLOCK</a> structure.


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
Set the <b>ObjectType</b>  member to an <a href="..\ndkpi\ne-ndkpi-_ndk_object_type.md">NDK_OBJECT_TYPE</a> value.

</li>
<li>
Set the  <b>NdkReserved</b> member to zero. The NDK provider must not modify this member until the object is closed.

</li>
</ul>



## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_invalidate.md">NDK_FN_INVALIDATE</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_object_header_reserved_block.md">NDK_OBJECT_HEADER_RESERVED_BLOCK</a>



<a href="..\ndkpi\ne-ndkpi-_ndk_object_type.md">NDK_OBJECT_TYPE</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_shared_endpoint.md">NDK_SHARED_ENDPOINT</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_mw.md">NDK_MW</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_OBJECT_HEADER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

