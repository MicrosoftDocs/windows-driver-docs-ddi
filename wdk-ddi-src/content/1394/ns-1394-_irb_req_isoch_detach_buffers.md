---
UID: NS:1394._IRB_REQ_ISOCH_DETACH_BUFFERS
title: "_IRB_REQ_ISOCH_DETACH_BUFFERS"
author: windows-driver-content
description: This structure contains the fields required to carry out a IsochDetachBuffers request.
old-location: ieee\irb_req_isoch_detach_buffers.htm
old-project: IEEE
ms.assetid: 60ED83BD-4AFA-432F-B918-9006815C8D47
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 1394/IRB_REQ_ISOCH_DETACH_BUFFERS, IRB_REQ_ISOCH_DETACH_BUFFERS structure [Buses], IRB_REQ_ISOCH_DETACH_BUFFERS, IEEE.irb_req_isoch_detach_buffers, _IRB_REQ_ISOCH_DETACH_BUFFERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_ISOCH_DETACH_BUFFERS
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_DETACH_BUFFERS
---

# _IRB_REQ_ISOCH_DETACH_BUFFERS structure


## -description


This structure contains the fields required to carry out a IsochDetachBuffers request.


## -syntax


````
typedef struct _IRB_REQ_ISOCH_DETACH_BUFFERS {
  HANDLE            hResource;
  ULONG             nNumberOfDescriptors;
  PISOCH_DESCRIPTOR pIsochDescriptor;
} IRB_REQ_ISOCH_DETACH_BUFFERS;
````


## -struct-fields




### -field hResource

Specifies the resource handle to detach buffers from.


### -field nNumberOfDescriptors

Specifies the number of elements in the <b>pIsochDescriptor</b> array.


### -field pIsochDescriptor

Points to an array of ISOCH_DESCRIPTOR structures that describe the buffers to be detached. The device driver should use the same ISOCH_DESCRIPTOR structure for a buffer that it used to attach the buffer.

