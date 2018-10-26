---
UID: NS:1394._IRB_REQ_ISOCH_ATTACH_BUFFERS
title: "_IRB_REQ_ISOCH_ATTACH_BUFFERS"
author: windows-driver-content
description: This structure contains the fields required for the 1394 bus driver to carry out a IsochAttachBuffers request.
old-location: ieee\irb_req_isoch_attach_buffers.htm
tech.root: IEEE
ms.assetid: 7EA6E82C-D803-48CD-9955-CF576BF978CA
ms.date: 02/15/2018
ms.keywords: 1394/IRB_REQ_ISOCH_ATTACH_BUFFERS, IEEE.irb_req_isoch_attach_buffers, IRB_REQ_ISOCH_ATTACH_BUFFERS, IRB_REQ_ISOCH_ATTACH_BUFFERS structure [Buses], _IRB_REQ_ISOCH_ATTACH_BUFFERS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1394.h
api_name:
-	IRB_REQ_ISOCH_ATTACH_BUFFERS
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_ATTACH_BUFFERS
---

# _IRB_REQ_ISOCH_ATTACH_BUFFERS structure


## -description


This structure contains the fields required for the 1394 bus driver to carry out a IsochAttachBuffers request.


## -struct-fields




### -field hResource

Specifies the resource handle to attach buffers to.


### -field nNumberOfDescriptors

Specifies the number of elements in the <b>pIsochDescriptor</b> array.


### -field pIsochDescriptor

Points to an array of ISOCH_DESCRIPTOR structures that describe the buffers to be attached, and the parameters that specify how each buffer is to be used.

