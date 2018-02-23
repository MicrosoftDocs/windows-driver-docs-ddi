---
UID: NS:poscx._POS_CX_ATTRIBUTES
title: "_POS_CX_ATTRIBUTES"
author: windows-driver-content
description: The POS_CX_ATTRIBUTES structure contains pointers to event callback functions implemented by the client driver.
old-location: pos\pos_cx_attributes.htm
old-project: pos
ms.assetid: A91B8EAA-2FCB-4468-8CF3-A3C4D9D7E355
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PPOS_CX_ATTRIBUTES structure pointer, _POS_CX_ATTRIBUTES, POS_CX_ATTRIBUTES structure, POS_CX_ATTRIBUTES, poscx/POS_CX_ATTRIBUTES, PPOS_CX_ATTRIBUTES, pos.pos_cx_attributes, poscx/PPOS_CX_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: poscx.h
req.include-header: Poscx.h
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
-	poscx.h
apiname:
-	POS_CX_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: POS_CX_ATTRIBUTES
req.product: Windows 10 or later.
---

# _POS_CX_ATTRIBUTES structure


## -description


The POS_CX_ATTRIBUTES structure contains pointers to event callback functions implemented by the client driver.

Use <a href="..\poscx\nf-poscx-pos_cx_attributes_init.md">POS_CX_ATTRIBUTES_INIT</a> to initialize this structure.


## -syntax


````
typedef struct _POS_CX_ATTRIBUTES {
  PFN_POS_CX_DEVICE_OWNERSHIP_CHANGE EvtDeviceOwnershipChange;
  PFN_POS_CX_DEVICE_REMOTE_CLAIM     EvtDeviceRemoteClaim;
  PFN_POS_CX_DEVICE_REMOTE_RELEASE   EvtDeviceRemoteRelease;
  PFN_POS_CX_DEVICE_REMOTE_RETAIN    EvtDeviceRemoteRetain;
} POS_CX_ATTRIBUTES, *PPOS_CX_ATTRIBUTES;
````


## -struct-fields




### -field EvtDeviceOwnershipChange

A pointer to an <a href="..\poscx\nc-poscx-evt_pos_cx_device_ownership_change.md">EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE</a> callback function.


### -field EvtDeviceRemoteClaim

A pointer to an <a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_claim.md">EVT_POS_CX_DEVICE_REMOTE_CLAIM</a> callback function.


### -field EvtDeviceRemoteRelease

A pointer to an <a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_release.md">EVT_POS_CX_DEVICE_REMOTE_RELEASE</a> callback function.


### -field EvtDeviceRemoteRetain

A pointer to an <a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_retain.md">EVT_POS_CX_DEVICE_REMOTE_RETAIN</a> callback function.


## -see-also

<a href="..\poscx\nf-poscx-poscxinit.md">PosCxInit</a>



<a href="..\poscx\nf-poscx-pos_cx_attributes_init.md">POS_CX_ATTRIBUTES_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20POS_CX_ATTRIBUTES structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

