---
UID: NS:ntddndis._NDIS_OPER_STATE
title: _NDIS_OPER_STATE
author: windows-driver-content
description: The NDIS_OPER_STATE structure provides the current operational state of an NDIS network interface.
old-location: netvista\ndis_oper_state.htm
old-project: netvista
ms.assetid: c08f8bcd-23fc-445c-9c42-e5c4edc75d78
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_OPER_STATE, *PNDIS_OPER_STATE, NDIS_OPER_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_OPER_STATE
req.alt-loc: ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PNDIS_OPER_STATE, NDIS_OPER_STATE
---

# _NDIS_OPER_STATE structure



## -description
The NDIS_OPER_STATE structure provides the current operational state of an NDIS network
  interface.



## -syntax

````
typedef struct _NDIS_OPER_STATE {
  NDIS_OBJECT_HEADER Header;
  NET_IF_OPER_STATUS OperationalStatus;
  ULONG              OperationalStatusFlags;
} NDIS_OPER_STATE, *PNDIS_OPER_STATE;
````


## -struct-fields

### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_OPER_STATE structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_OPER_STATE_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_OPER_STATE_REVISION_1.


### -field OperationalStatus

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568746">NET_IF_OPER_STATUS</a> operational status
     type.


### -field OperationalStatusFlags

This member provides the reason why the 
     <b>OperationalStatus</b> member is set to <b>NET_IF_OPER_STATUS_DOWN</b> or NET_IF_OPER_STATUS_DORMANT. This
     member is a ULONG value that contains a bitwise OR of a combination of the following flags:
     




### -field NET_IF_OPER_STATUS_DOWN_NOT_AUTHENTICATED

The operational status is set to <b>NET_IF_OPER_STATUS_DOWN</b> because the default port of the
       miniport adapter is not authenticated.


### -field NET_IF_OPER_STATUS_DOWN_NOT_MEDIA_CONNECTED

The operational status is set to <b>NET_IF_OPER_STATUS_DOWN</b> because the miniport adapter is not in
       a media-connected state.


### -field NET_IF_OPER_STATUS_DORMANT_PAUSED

The operational status is set to <b>NET_IF_OPER_STATUS_DORMANT</b> because the miniport adapter is in
       the paused or pausing state.


### -field NET_IF_OPER_STATUS_DORMANT_LOW_POWER

The operational status is set to <b>NET_IF_OPER_STATUS_DORMANT</b> because the miniport adapter is in a
       low power state.

</dd>
</dl>

## -remarks
For the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567406">NDIS_STATUS_OPER_STATUS</a> status
    indication, NDIS supplies an NDIS_OPER_STATE structure in the 
    <b>StatusBuffer</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a> structure.

NDIS_STATUS_OPER_STATUS indicates the current operational state of an NDIS network interface to
    overlying drivers.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567406">NDIS_STATUS_OPER_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568746">NET_IF_OPER_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_OPER_STATE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

