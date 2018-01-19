---
UID: NI:nfcsedev.IOCTL_NFCSE_SET_ROUTING_TABLE
title: IOCTL_NFCSE_SET_ROUTING_TABLE
author: windows-driver-content
description: Configures NFC controller listen mode routing table.
old-location: nfpdrivers\ioctl_nfcse_set_routing_table.htm
old-project: nfpdrivers
ms.assetid: 54B37EC0-C38A-479C-A45F-424963C4D89A
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFCSE_SET_ROUTING_TABLE
req.alt-loc: nfcsedev.h
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
req.typenames: *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
---

# IOCTL_NFCSE_SET_ROUTING_TABLE IOCTL



## -description
Configures NFC controller listen mode routing table. Note that caller has to send complete listen mode routing information in a single call. The caller shall ensure that routing table is less than the cbMaxRoutingTableSize value defined in 4.2.5.1. The total size is computed as per NFC NCI standard sec 6.3.2 and is equal to Number of AID based routes x 4 + sum of cbAid + Number of technology based routes x 5 + Number of protocol based routes x 5. The caller shall ensure that values for technology- and protocol-based routes are conformant to NCI NFC spec sec 6.3.2.





## -ioctlparameters

### -input-buffer

<a href="..\nfcsedev\ns-nfcsedev-_secure_element_routing_table.md"> SECURE_ELEMENT_ROUTING_TABLE</a> containing all currently configured routing entries.



### -input-buffer-length

<text></text>

### -output-buffer
None


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks
The following are requirements that the driver must adhere to.

<ul>
<li>This IOCTL is sent on a handle with a ‘SEManage’ relative file name, otherwise the driver MUST complete it with STATUS_INVALID_DEVICE_STATE.

</li>
<li>The driver shall have initial default listen mode routing table entries that route RF technologies A, B, and F and/or ISO-DEP protocol routed to UICC SE if present. These routing entries may later be overridden by new listen mode routing table configuration initiated by device host.

</li>
<li>The driver shall ensure that protocol NFC-DEP is mapped to device host at all times. Even if the caller doesn’t specify this, the driver needs to add this rule implicitly.

</li>
<li>If this IOCTL is issued when the NFCC is in RF discovery state, the driver needs to put the NFCC into RF idle state, configure the routing table, and restart RF discovery.</li>
</ul>
</p>