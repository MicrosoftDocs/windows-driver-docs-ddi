---
UID: NS:1394._IRB_REQ_ISOCH_LISTEN
title: "_IRB_REQ_ISOCH_LISTEN"
author: windows-driver-content
description: This structure contains the fields necessary to carry out a ReqIsochListen request.
old-location: ieee\irb_req_isoch_listen.htm
old-project: IEEE
ms.assetid: 9B0590F4-E9B3-4999-99BD-BDB1EA413FF4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1394/IRB_REQ_ISOCH_LISTEN, IEEE.irb_req_isoch_listen, IRB_REQ_ISOCH_LISTEN, IRB_REQ_ISOCH_LISTEN structure [Buses], _IRB_REQ_ISOCH_LISTEN
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
-	IRB_REQ_ISOCH_LISTEN
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_LISTEN
---

# _IRB_REQ_ISOCH_LISTEN structure


## -description


This structure contains the fields necessary to carry out a ReqIsochListen request.


## -syntax


````
typedef struct _IRB_REQ_ISOCH_LISTEN {
  HANDLE     hResource;
  ULONG      fulFlags;
  CYCLE_TIME StartTime;
} IRB_REQ_ISOCH_LISTEN;
````


## -struct-fields




### -field hResource

Specifies the resource handle to use in reading data.


### -field fulFlags

Reserved. Device drivers must set this to zero.


### -field StartTime

Specifies the cycle time to begin reading data. This member is used only if the driver specified the RESOURCE_SYNCH_ON_TIME flag when it allocated the resource handle passed in <b>u.IsochListen.hResource</b>. (The timing resolution is per isochronous cycle, so the <b>CycleOffset</b> member of <b>StartTime</b> is not used.)


## -remarks



The bus driver completes this request once it has successfully scheduled the isochronous listen operation. It does not wait for the data transfer to finish, or even begin, before it completes the request.

Listening on a channel may begin immediately, or it may be synchronized to an event. If the driver set the RESOURCE_SYNCH_ON_TIME flag on the REQUEST_ISOCH_ALLOCATE_RESOURCES request that returned the resource handle, then the listen begins on the cycle count specified in <b>StartTime</b>. Additional synchronization options may be set for each buffer within that buffer's ISOCH_DESCRIPTOR structure.



